---
name: ai-docs-generate
description: 'Generate WDK DDI API reference documentation pages from source code and stubs. Use when: writing API docs, generating reference pages, documenting a header, creating DDI documentation.'
argument-hint: 'Specify a header name (e.g. soundwireclass) and the path to the CSV file.'
---

# Generate API Docs

Generate complete API reference documentation pages for WDK DDI entities by combining stub files, OS source code declarations, and supplemental information from published docs.

**No local repo clones required.** All repo interactions use the Azure DevOps REST API. OS source lookups use the `substrate-mcp` MCP server.

## Parameters

| Parameter | Value |
|-----------|-------|
| ADO Org | `https://dev.azure.com/cpubwin` |
| ADO Project | `drivers` |
| Docs Repo | `wdk-ddi` (branches: `main`, `stubs/main`) |
| Published Docs Repo | `windows-driver-docs-ddi` (branch: `staging`) |
| Content Path | `wdk-ddi-src/content/{header}/` |
| Stubs Branch | `stubs/main` (default; user may specify alternate) |
| Header Name | Provided by the user (without `.h` extension for path operations) |
| CSV Path | Provided by the user at any local path (e.g. `D:\work\soundwireclass.csv`) |
| Working Directory | Derived from CSV path (parent folder of the CSV file) |
| Output Path | `{working_dir}\output\` |
| Style Guide | Read remotely from `wdk-ddi` repo: `.github/copilot-instructions.md` on `main` |

## Prerequisites

- The user provides a header name and a path to a CSV file (pre-provided or from the `ai-docs-inventory` skill). **That is the only user requirement.**
- The `substrate-mcp` MCP server must be accessible for source code retrieval
- The `microsoft.docs.mcp` MCP server should be accessible for supplemental info (non-fatal if unavailable)
- Azure CLI (`az`) should be available for auth token acquisition. If not, the agent will prompt for an ADO Personal Access Token (PAT) once per session.

## Procedure

1. Strip the `.h` extension from the user-provided header name to get `{header}` (e.g. `soundwireclass.h` → `soundwireclass`).

2. **Resolve paths.** The user provides a CSV path. Derive the working directory from it:

   ```powershell
   $csvPath = "{user-provided CSV path}"
   if (-not (Test-Path $csvPath)) {
       Write-Error "CSV not found at $csvPath. Please provide the CSV file first."
       return
   }
   $workingDir = Split-Path $csvPath -Parent
   $outputDir = Join-Path $workingDir "output"
   Import-Csv $csvPath
   ```

   If the CSV does not exist, inform the user and stop.

3. **Obtain ADO auth token.** Try Azure CLI first, then fall back to prompting for a PAT:

   ```powershell
   try {
       $token = (az account get-access-token --resource 499b84ac-1321-427f-aa17-267ca6975798 --query accessToken -o tsv 2>$null)
       if (-not $token) { throw "No token" }
       $headers = @{ Authorization = "Bearer $token" }
   } catch {
       $pat = Read-Host "Enter ADO PAT (scope: Code Read)"
       $base64 = [Convert]::ToBase64String([Text.Encoding]::ASCII.GetBytes(":$pat"))
       $headers = @{ Authorization = "Basic $base64" }
   }
   $adoBase = "https://dev.azure.com/cpubwin/drivers/_apis/git/repositories"
   ```

4. **Read the style guide** remotely from the wdk-ddi repo to ensure all formatting rules are followed:

   ```powershell
   $styleGuide = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?path=.github/copilot-instructions.md&versionDescriptor.version=main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
   ```

5. Parse the CSV file to get the list of target filenames. The CSV has a header row and one `filename` column with paths like `wdk-ddi-src/content/{header}/{filename}.md`.

6. Create the output directory if it doesn't exist; if it does, clear it:

   ```powershell
   if (Test-Path $outputDir) {
       Remove-Item "$outputDir\*" -Force -ErrorAction SilentlyContinue
   } else {
       New-Item -ItemType Directory -Path $outputDir -Force | Out-Null
   }
   ```

7. For each target file listed in the CSV, **skip `index.md`** (the header landing page is handled separately in step 8).

   For each remaining target file:

   ### a. Get the stub or existing file

   Use the ADO REST API to check if the file already exists on `main`:
   ```powershell
   # List files on main branch
   $mainFiles = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?scopePath=wdk-ddi-src/content/{header}/&recursionLevel=OneLevel&versionDescriptor.version=main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
   ```
   If the target filename appears in the listing, retrieve it from `main` and use its content as the starting point — preserve existing text. **Only write the file to the output folder if you make changes.** Do not copy unchanged files.
   ```powershell
   $content = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?path=wdk-ddi-src/content/{header}/{filename.md}&versionDescriptor.version=main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
   $content | Out-File -FilePath (Join-Path $outputDir "{filename.md}") -Encoding utf8
   ```

   If it does not exist on `main`, retrieve the stub from the stubs branch:
   ```powershell
   $content = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?path=wdk-ddi-src/content/{header}/{filename.md}&versionDescriptor.version=stubs/main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
   $content | Out-File -FilePath (Join-Path $outputDir "{filename.md}") -Encoding utf8
   ```

   ### b. Retrieve source declaration from the OS source tree

   Use the `substrate-mcp` MCP server to find the API's source declaration:

   - Extract the API name from the filename (e.g. `nf-soundwireclass-somefunc.md` → `SomeFunc`)
   - Search for the definition:
     ```
     search_code(query="def:{ApiName}", ext="h")
     ```
   - If `def:` doesn't find it, try keyword search:
     ```
     search_code(query="{ApiName}", ext="h", path="**/{header}.h")
     ```
   - Once found, use `get_file_content` with a line range to retrieve the full declaration including:
     - SAL annotations (`_In_`, `_Out_`, `_Inout_`, `_In_opt_`, `_Out_opt_`, `_Reserved_`)
     - Return type
     - All parameter names and types
     - Any adjacent comments describing the function
   - For structures/enums, retrieve the full type definition with all fields/values

   ### c. Gather supplemental information

   Use the `microsoft.docs.mcp` server's `microsoft_docs_search` tool to search for any existing published docs or related conceptual content for the API:
   ```
   microsoft_docs_search(query="{ApiName} WDK driver")
   ```

   ### d. Find formatting models

   Find 1-2 completed reference pages in the same header folder to use as formatting models. Use the ADO REST API to list files, then retrieve them:
   ```powershell
   # List existing completed docs of the same entity type in the {header} folder
   $mainFiles = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?scopePath=wdk-ddi-src/content/{header}/&recursionLevel=OneLevel&versionDescriptor.version=main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
   # Filter for files matching the same prefix (e.g. "nf-") and pick 1-2
   ```
   Then read the model files:
   ```powershell
   $modelContent = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?path=wdk-ddi-src/content/{header}/{model-filename.md}&versionDescriptor.version=main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
   ```
   If no completed pages exist in the same folder, look in a related header folder. Read these model files to match their style.

   ### e. Write the completed documentation page

   Write the completed file to `{outputDir}\{filename.md}`. Follow these rules:

   #### YAML Frontmatter
   - Preserve all existing metadata from the stub
   - Add `ai-usage: ai-assisted` if not already present
   - Set `techroot` to the same value as existing files in the same header folder. If no existing files, prompt user for value.
   - Ensure `ms.date` is set to today's date in `MM/DD/YYYY` format
   - Verify `req.header`, `f1_keywords`, `api_name`, `topic_type` are correct
   - **`req.header` uses lowercase** (e.g. `classpnp.h`). **`req.include-header` uses sentence capitalization** (e.g. `Classpnp.h`). Note that `req.include-header` does not always require a value — omit it or leave it empty when an include header is not applicable.
   - **`req.construct-type` for macros:** If the source declaration is a preprocessor macro (`#define`), set `req.construct-type: macro`, not `function`. The file prefix remains `nf-` and the title should say "macro" (e.g. `CLEAR_FLAG_NOFENCE macro (classpnp.h)`).
   - **Leading underscores in UIDs:** If the stub file's UID uses a leading underscore (e.g. `NE:wdbgexts._POOL_HEADER_FIELD_NAME`), preserve that underscore in the UID of the generated document. However, all customer-facing content (title, description, headings, prose) must use the version without the leading underscore (e.g. `POOL_HEADER_FIELD_NAME`). For `api_name:` and `f1_keywords:`, include **both** versions — the underscored name and the public name — so the page is discoverable by either form.

   #### Content Sections (in order)

   **`## -description`**
   - Write a concise one-paragraph summary of what the API does
   - Focus on the public API behavior, not internal implementation
   - Use **bold** for API names referenced in text

   **`## -parameters`** (functions/callbacks/macros)
   - One `### -param {Name} [{direction}]` subsection per parameter
   - Map SAL annotations to direction labels:
     - `_In_` → `[in]`
     - `_Out_` → `[out]`
     - `_Inout_` → `[in, out]`
     - `_In_opt_` → `[in, optional]`
     - `_Out_opt_` → `[out, optional]`
     - `_Reserved_` → `[in]` with note "Reserved. Must be zero/NULL."
   - Describe each parameter concisely
   - **Macro parameters requiring address-of (`&`):** If the macro implementation takes the address of a parameter (e.g. `&(Flags)`), describe the parameter as "An addressable {type} storage location (such as a variable or structure field)" rather than "A {type} value." A macro that takes `&(param)` requires an lvalue, not an arbitrary expression.

   **`## -struct-fields`** (structures only)
   - One `### -field {FieldName}` subsection per field
   - **Union types use the structure classification.** If the C source declares a `union`, it is still documented with the `ns-` file prefix and `req.construct-type: structure`. All prose (description, field descriptions, remarks, and cross-references from other pages) must call it a "structure", never a "union." The heading should read `# {NAME} structure`, not `# {NAME} union`.

   **`## -enum-fields`** (enumerations only)
   - One `### -field {ValueName}:{NumericValue}` subsection per value (if numeric value is known)

   **`## -ioctlparameters`** (IOCTLs only)
   - Document input buffer, output buffer, and status block

   **`## -returns`** (functions with return values)
   - Document the return type and possible return values
   - For NTSTATUS returns, list common status codes

   **`## -remarks`**
   - Add usage notes, IRQL requirements, important caveats
   - Include code examples when helpful
   - If the entity is an extended version (ends in `Ex`, or a number like `2`, `3`, or `V2`), reference the base entity and document only the extensions
   - Don't generate repetitive information
   - Don't include internal implementation details

   **`## -see-also`**
   - List related APIs as relative Markdown links, one per line
   - Write entries in **alphabetical order**
   - Use relative paths: `[**OtherFunc**](nf-{header}-otherfunc.md)` for same-header APIs
   - Use `../` paths for cross-header: `[**CrossFunc**](../otherheader/nf-otherheader-crossfunc.md)`

   #### Formatting Rules
   - Use **bold** for API names in prose: `**IoCreateFile**`
   - Use *italic* for parameter name references in prose: `*DesiredAccess*`
   - Use site-relative links for learn.microsoft.com content: `[title](/windows-hardware/drivers/...)`
   - Code blocks use `cpp` language tag
   - Ensure exactly one blank line at the end of the file

8. Handle the header landing page (`index.md`). The landing page is automatically updated during the build to reflect the current API set, so it almost never needs manual editing once published.

   - Check if `index.md` already exists on `main` of `wdk-ddi` or `staging` of the published docs repo using the ADO REST API:
     ```powershell
     # Check wdk-ddi main
     $mainItems = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?scopePath=wdk-ddi-src/content/{header}/&recursionLevel=OneLevel&versionDescriptor.version=main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
     
     # Check windows-driver-docs-ddi staging
     $pubItems = Invoke-RestMethod -Uri "$adoBase/windows-driver-docs-ddi/items?scopePath=wdk-ddi-src/content/{header}/&recursionLevel=OneLevel&versionDescriptor.version=staging&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
     ```
   - If `index.md` appears in either listing, **skip it** — no action needed.
   - If no published `index.md` exists, retrieve the stub from the stubs branch and save it as `index.md`:
     ```powershell
     $stubContent = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?path=wdk-ddi-src/content/{header}/na-{header}.md&versionDescriptor.version=stubs/main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
     $stubContent | Out-File -FilePath (Join-Path $outputDir "index.md") -Encoding utf8
     ```
   - **Content rules for a new `index.md`:** After retrieving the stub, ensure the `## -description` section follows this strict format:
     1. Write **no more than one sentence** describing the header.
     2. Immediately follow it with: `This header is used by [{tech.root display name}](../{tech.root}/index.md). For more information, see: [{tech.root display name}](../{tech.root}/index.md).`
        Replace `{tech.root display name}` with the human-readable technology area name and `{tech.root}` with the `tech.root` value from the frontmatter (e.g. `_netvista` → `[Networking](/windows-hardware/drivers/ddi/_netvista/)`).
     3. **Do not add any sections after `-description`.** There must be no `-remarks` or `-see-also` sections in an `index.md` file.

9. **Close editor tabs.** After all files have been written to `{outputDir}`, close all open editor tabs so the workspace is not cluttered with generated files. Run the VS Code command `workbench.action.closeAllEditors` to close them.

10. **Pause for human review.** Display:
   - List of all generated/updated files in `{outputDir}`
   - For each file, show the first 20 lines (frontmatter + description) as a sample
   - Highlight any metadata fields marked as TODO that the user should fill in manually (e.g. `req.lib`, `req.dll`, `req.irql` if not determinable from source)
   - Prompt the user to review the markdown files at: `{outputDir}`

11. **Continue or stop.** Ask the user:

    > Docs generated and ready for review in `{outputDir}`. **Please review the files before proceeding** — once submitted, a PR will be created in the wdk-ddi repo. Press **y** to submit them as a PR, or type **n** to stop and review further.

    - If the user types **y**: automatically invoke the `ai-docs-submit` skill, passing the same header name. Behave as if the user typed `/ai-docs-submit {header}`.
    - If the user types **n**: stop and tell them they can run it later with: `/ai-docs-submit {header}`

    > **Tip:** To run all three steps (inventory → generate → submit) with no interaction, use the `ai-docs-autopilot` skill instead.
