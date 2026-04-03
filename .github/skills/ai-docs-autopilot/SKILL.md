---
name: ai-docs-autopilot
description: 'End-to-end autopilot: inventory, generate, and submit WDK DDI API reference docs from a CSV file with no user interaction. Use when: running the full doc pipeline unattended, auto-generating and submitting DDI docs.'
argument-hint: 'Specify a header name (e.g. soundwireclass) and the path to the CSV file.'
---

# Autopilot: Inventory → Generate → Submit

Run the full DDI documentation pipeline end-to-end with no user interaction. The agent inventories APIs from a CSV, generates documentation pages, and submits them as a PR — stopping only on error.

**No local repo clones required.** All repo interactions use the Azure DevOps REST API. OS source lookups use the `substrate-mcp` MCP server.

## Parameters

| Parameter | Value |
|-----------|-------|
| ADO Org | `https://dev.azure.com/cpubwin` |
| ADO Project | `drivers` |
| Docs Repo | `wdk-ddi` (branches: `main`, `stubs/main`) |
| Published Docs Repo | `wdk-ddi-build` (branch: `live`) |
| Published Docs Repo (staging) | `windows-driver-docs-ddi` (branch: `staging`) |
| Content Path | `wdk-ddi-src/content/{header}/` |
| Stubs Branch | `stubs/main` (default; user may specify alternate like `stubs/release-amethyst`) |
| Header Name | Provided by the user (e.g. `soundwireclass`) |
| CSV Input | Provided by the user at any local path (e.g. `D:\work\soundwireclass.csv`) |
| Working Directory | Derived from CSV path (parent folder of the CSV file) |
| Output Path | `{working_dir}\output\` |
| Style Guide | Read remotely from `wdk-ddi` repo: `.github/copilot-instructions.md` on `main` |
| User Alias | Auto-detected from CSV `Owner` column, `$env:USERNAME`, or `az account show` |
| Source Branch | Auto-generated as `{user-alias}/{header}-update` |

## Prerequisites

- The user provides a header name and a path to a CSV file. **That is the only user requirement.**
- Azure CLI (`az`) should be available for auth token acquisition. If not, the agent will prompt for an ADO Personal Access Token (PAT) once per session.
- The `substrate-mcp` MCP server must be accessible for source code retrieval.
- The `microsoft.docs.mcp` MCP server should be accessible for supplemental info (non-fatal if unavailable).

## Autopilot Mode

This skill runs **all three phases** (inventory, generate, submit) in sequence with **no user interaction** between them. The process only stops if an error is encountered. Progress is reported to the console after each phase.

---

# Phase 1: Inventory

Read a pre-provided CSV of target API filenames, cross-reference each entry against existing docs, stubs, and published content via the ADO REST API, classify their status, and finalize the CSV.

## File Naming Conventions

Map each API entity to a filename using these prefixes:

| Prefix | Type | Example |
|--------|------|---------|
| `nf` | Function | `nf-soundwireclass-somefunc.md` |
| `ns` | Structure | `ns-soundwireclass-some_struct.md` |
| `ne` | Enumeration | `ne-soundwireclass-some_enum.md` |
| `nc` | Callback | `nc-soundwireclass-evt_some_callback.md` |
| `ni` | IOCTL | `ni-soundwireclass-ioctl_some_code.md` |
| `nn` | Interface | `nn-soundwireclass-isome_interface.md` |
| `nl` | Class | `nl-soundwireclass-some_class.md` |

The filename pattern is: `{prefix}-{header}-{api_name_lowercase}.md`

Where `{header}` is the header name without the `.h` extension.

### Header Landing Page

On the stubs branch, the header landing page is always named `na-{header}.md`. When it is copied to `wdk-ddi-src/content/{header}/` on the `main` branch, it is renamed to `index.md`. In the published docs repo, it also appears as `index.md`. When cross-referencing, check for `na-{header}.md` on the stubs branch and `index.md` on `main` and in the published docs repo.

### Legacy Filename Exceptions

Some existing files in the published docs repo or on `main` may have non-standard filenames (e.g. an extra underscore like `ns-header-_struct_name.md` instead of `ns-header-struct_name.md`). These are historical naming errors. **Do not rename existing files** — doing so would break published links. When cross-referencing, also check for these variant filenames. For **new** APIs, always use the approved naming convention.

## Execution Strategy

**Write all PowerShell logic into a single self-contained `.ps1` script file, then execute it in one terminal call.** Do NOT run ADO REST calls or variable assignments as separate interactive terminal commands — PowerShell variables are lost between terminal invocations and long-running commands may time out and get moved to the background, breaking the workflow.

The pattern is:
1. Create a script file at `{workingDir}\inventory.ps1` containing all the logic from the Inventory Procedure below. **Use the `create_file` tool** to write the script — this auto-saves the file to disk immediately, avoiding any unsaved-buffer issues.
2. Execute it in a single terminal call: `powershell -ExecutionPolicy Bypass -File "{workingDir}\inventory.ps1"`
3. Parse the script's console output to present results to the user.

The script should accept no parameters — hardcode the `{header}`, `{csvPath}`, `{workingDir}`, and `{userAlias}` values directly into the generated script.

## Inventory Procedure

Write a single `inventory.ps1` script that performs all of the following steps, then execute it.

1. Strip the `.h` extension from the user-provided header name to get `{header}` (e.g. `soundwireclass.h` → `soundwireclass`).

2. **Resolve the user alias** for branch naming (`{user-alias}`). Try these sources in order and use the first non-empty value:
   a. The `Owner` column from the CSV (if all rows share the same value).
   b. The Windows username: `$env:USERNAME`.
   c. The Azure CLI identity: `az account show --query user.name -o tsv`, extracting the alias portion before `@`.
   
   The resolved alias is used later for the branch name `{user-alias}/{header}-update`. Hardcode it into the generated scripts.

3. **Resolve paths.** The user provides a CSV path. Derive the working directory from it. The script should validate the CSV exists and read it:

   ```powershell
   $ErrorActionPreference = "Stop"
   $header = "{header}"
   $csvPath = "{user-provided CSV path}"
   $workingDir = Split-Path $csvPath -Parent

   if (-not (Test-Path $csvPath)) {
       Write-Error "CSV not found at $csvPath."
       exit 1
   }
   ```

   Read the CSV:
   ```powershell
   $csvData = Import-Csv $csvPath
   ```

   The CSV has a header row. Look for a column containing file paths (commonly `FilePath` or `filename`) with values like `wdk-ddi-src/content/{header}/{filename}.md`. Filter to rows with valid `.md` paths.

3. **Obtain ADO auth token.** Try Azure CLI first, then fail with a clear message (PAT prompting cannot work inside a non-interactive script):

   ```powershell
   $token = (az account get-access-token --resource 499b84ac-1321-427f-aa17-267ca6975798 --query accessToken -o tsv 2>$null)
   if (-not $token) {
       Write-Error "Failed to get ADO token. Run 'az login' first, or set `$env:ADO_PAT before running."
       exit 1
   }
   $h = @{ Authorization = "Bearer $token" }
   $adoBase = "https://dev.azure.com/cpubwin/drivers/_apis/git/repositories"
   ```

4. For each entry in the CSV, extract the target filename from the path (e.g. `wdk-ddi-src/content/{header}/nf-soundwireclass-somefunc.md` → `nf-soundwireclass-somefunc.md`).

5. **List all files in the directory on each branch** (one API call per branch, not per file). This detects legacy filename variants (see [Legacy Filename Exceptions](#legacy-filename-exceptions)):

   ```powershell
   # List files on main branch of wdk-ddi
   try {
       $r1 = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?scopePath=wdk-ddi-src/content/{header}/&recursionLevel=OneLevel&versionDescriptor.version=main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $h
       $mainFiles = @($r1.value | Where-Object { $_.path -like "*.md" } | ForEach-Object { Split-Path $_.path -Leaf })
   } catch { $mainFiles = @() }

   # List files on stubs branch of wdk-ddi
   try {
       $r2 = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?scopePath=wdk-ddi-src/content/{header}/&recursionLevel=OneLevel&versionDescriptor.version=stubs/main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $h
       $stubFiles = @($r2.value | Where-Object { $_.path -like "*.md" } | ForEach-Object { Split-Path $_.path -Leaf })
   } catch { $stubFiles = @() }

   # List files on live branch of wdk-ddi-build (published docs)
   try {
       $r3 = Invoke-RestMethod -Uri "$adoBase/wdk-ddi-build/items?scopePath=wdk-ddi-src/content/{header}/&recursionLevel=OneLevel&versionDescriptor.version=live&versionDescriptor.versionType=branch&api-version=7.0" -Headers $h
       $pubFiles = @($r3.value | Where-Object { $_.path -like "*.md" } | ForEach-Object { Split-Path $_.path -Leaf })
   } catch { $pubFiles = @() }

   Write-Host "Main: $($mainFiles.Count) files, Stubs: $($stubFiles.Count) files, Published: $($pubFiles.Count) files"
   ```

   Compare each expected filename against the directory listings. If a file exists with a minor variant (e.g. `ns-header-_struct_name.md` instead of `ns-header-struct_name.md`), treat it as a match — the doc exists under the legacy name. **Use the legacy filename in the CSV** (do not rename it).

   a. Check if the file exists on `main` of `wdk-ddi` (look for the filename in `$mainFiles`).

   b. Check if a stub exists on the stubs branch (look for the filename in `$stubFiles`).

   c. Check if the file exists on `live` of the published docs repo `wdk-ddi-build` (look for the filename in `$pubFiles`).

6. Classify each API into one of three categories:
   - **new**: Stub exists on `stubs/main` but no completed doc on `main`
   - **update**: File already exists on `main` — needs to be compared with the latest stub to identify changes
   - **stub not found**: No stub and no existing doc

7. **Output grouped results** to the console for the agent to parse and present:

   ```
   === New (ready to document) ===
   nf-soundwireclass-somefunc.md          (function)
   ns-soundwireclass-some_struct.md       (structure)

   === Update (existing doc, needs diff) ===
   nf-soundwireclass-otherfunc.md         (function)  [+2 params, -1 param, ~1 param]

   === Stub not found ===
   ne-soundwireclass-some_enum.md         (enumeration)
   ```

8. **Diff existing docs against stubs.** For each "update" entry, fetch the existing doc from `main` and the latest stub from `stubs/main` via the ADO REST API. Compare the parameter/field/value sections to identify:
   - **Added** parameters, fields, or enum values (present in stub but not in existing doc)
   - **Removed** parameters, fields, or enum values (present in existing doc but not in stub)
   - **Modified** parameters, fields, or enum values (present in both but with different types or descriptions)

   Output a per-file change summary (e.g. `[+2 params, -1 param, ~1 param]`) in the console results.

9. **Write the updated CSV** at the original CSV path. The format must be compatible with Phase 2:

   ```csv
   filename,status
   wdk-ddi-src/content/{header}/{filename1}.md,new
   wdk-ddi-src/content/{header}/{filename2}.md,update
   ```

   The script writes both "new" and "update" entries. "Stub not found" entries are excluded.

10. **Output a summary** to the console:
    - Number of APIs in the CSV by type
    - Number selected for documentation
    - Working directory: `{workingDir}`
    - CSV file location: `{csvPath}`

After the script finishes, the agent should verify the CSV was written successfully. If the inventory found zero entries for documentation (all "stub not found"), stop with an error. Otherwise, **proceed immediately to Phase 2** with no user prompt.

---

# Phase 2: Generate API Docs

Generate complete API reference documentation pages for WDK DDI entities by combining stub files, OS source code declarations, and supplemental information from published docs.

## Generate Procedure

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

   If the CSV does not exist, stop with an error.

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
   - Set `tech.root` to the same value as existing files in the same header folder. If no existing files in the folder (i.e. a brand-new API set), make an educated guess based on the header's source location, API naming patterns, and functionality (e.g. headers in `minkernel/` are typically `kernel`, networking headers are `netvista`, storage headers are `storage`, etc.). Log the guessed value and add a note for the user: `"NOTE: tech.root guessed as '{value}' — please verify this is correct."`
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

9. **Log progress.** After generation completes, display:
   - List of all generated/updated files in `{outputDir}`
   - For each file, show the first 20 lines (frontmatter + description) as a sample
   - Highlight any metadata fields marked as TODO that the user should fill in manually (e.g. `req.lib`, `req.dll`, `req.irql` if not determinable from source)

   Then **proceed immediately to Phase 3** with no user prompt.

---

# Phase 3: Submit as PR

Submit generated API reference documentation as a pull request to the `wdk-ddi` Azure DevOps repo using the ADO REST API.

**No local repo clone required.** Branch creation, file push, and PR creation are all done via the ADO REST API.

## Submit Procedure

1. Strip the `.h` extension from the user-provided header name to get `{header}` (e.g. `soundwireclass.h` → `soundwireclass`).

2. **Resolve paths.** The user provides the CSV path. Derive the working and output directories:

   ```powershell
   $csvPath = "{user-provided CSV path}"
   if (-not (Test-Path $csvPath)) {
       Write-Error "CSV not found at $csvPath."
       return
   }
   $workingDir = Split-Path $csvPath -Parent
   $outputDir = Join-Path $workingDir "output"
   $entries = Import-Csv $csvPath
   ```

   If the CSV does not exist, stop with an error. Use the CSV entries to identify the API entities for the commit message and PR description.

3. Verify the output directory exists and contains files:

   ```powershell
   $outputFiles = Get-ChildItem -Path $outputDir -Filter "*.md" -ErrorAction SilentlyContinue
   if (-not $outputFiles -or $outputFiles.Count -eq 0) {
       Write-Error "No generated docs found in $outputDir. Generation phase may have failed."
       return
   }
   ```

4. **Obtain ADO auth token.** Try Azure CLI first, then fall back to prompting for a PAT:

   ```powershell
   try {
       $token = (az account get-access-token --resource 499b84ac-1321-427f-aa17-267ca6975798 --query accessToken -o tsv 2>$null)
       if (-not $token) { throw "No token" }
       $headers = @{ Authorization = "Bearer $token"; "Content-Type" = "application/json" }
   } catch {
       $pat = Read-Host "Enter ADO PAT (scope: Code Read+Write, PR Contribute)"
       $base64 = [Convert]::ToBase64String([Text.Encoding]::ASCII.GetBytes(":$pat"))
       $headers = @{ Authorization = "Basic $base64"; "Content-Type" = "application/json" }
   }
   $adoBase = "https://dev.azure.com/cpubwin/drivers/_apis/git/repositories"
   ```

5. **Get the latest commit SHA on `main`.** This is required as the `oldObjectId` for the push:

   ```powershell
   $refs = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/refs?filter=heads/main&api-version=7.0" -Headers $headers
   $mainSha = $refs.value[0].objectId
   ```

6. **Determine change type for each file.** Check which files already exist on `main` to set the correct `changeType` (`add` vs `edit`):

   ```powershell
   $mainFiles = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/items?scopePath=wdk-ddi-src/content/{header}/&recursionLevel=OneLevel&versionDescriptor.version=main&versionDescriptor.versionType=branch&api-version=7.0" -Headers $headers
   $existingNames = $mainFiles.value | ForEach-Object { Split-Path $_.path -Leaf }
   ```

7. **Build the push payload.** Read each output file, base64-encode its content, and create the change entries:

   ```powershell
   $changes = @()
   foreach ($file in $outputFiles) {
       $contentBytes = [System.IO.File]::ReadAllBytes($file.FullName)
       $base64Content = [Convert]::ToBase64String($contentBytes)
       $repoPath = "/wdk-ddi-src/content/{header}/$($file.Name)"
       $changeType = if ($file.Name -in $existingNames) { "edit" } else { "add" }
       $changes += @{
           changeType = $changeType
           item = @{ path = $repoPath }
           newContent = @{
               content = $base64Content
               contentType = "base64encoded"
           }
       }
   }
   ```

8. **Generate the commit message.** Use the CSV entries to list the API entity names:

   ```
   Add/update API reference docs for {header}.h

   Documented {N} API entities:
   - {ApiName1} ({type})
   - {ApiName2} ({type})
   ...

   AI-assisted content generation.
   ```

9. **Log the push plan.** Display:
   - List of files to be pushed with their change types (`add` / `edit`)
   - Total file count
   - The generated commit message
   - The target branch name: `{user-alias}/{header}-update`

10. **Create or locate the branch.** This step MUST be completed separately before the push in step 11. The branch must exist and point to a real commit on `main` before any push is attempted.

    > **CRITICAL — Orphan commit prevention:** The `oldObjectId` used in the push (step 11) determines the **parent commit** of the new commit. If `oldObjectId` is set to `0000000000000000000000000000000000000000` (all zeros), the ADO pushes API creates an **orphan root commit with no parent**. The resulting commit tree will contain ONLY the files in the `changes` array — all other repository files will appear as deletions in any PR diff. **NEVER use all-zeros as `oldObjectId` in the pushes API.** Always use `$mainSha` or the branch's current commit SHA.

    First, check if the branch already exists:
    ```powershell
    $branchRef = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/refs?filter=heads/{user-alias}/{header}-update&api-version=7.0" -Headers $headers
    if ($branchRef.value.Count -gt 0) {
        # Branch exists — use its current SHA
        $branchSha = $branchRef.value[0].objectId
    } else {
        # Create the branch via the refs API (JSON array body)
        $createBranchPayload = "[{`"name`":`"refs/heads/{user-alias}/{header}-update`",`"oldObjectId`":`"0000000000000000000000000000000000000000`",`"newObjectId`":`"$mainSha`"}]"
        $refResult = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/refs?api-version=7.0" -Method Post -Headers $headers -Body $createBranchPayload
        $branchSha = $refResult.value[0].newObjectId
    }
    ```

    > **Important:** The `POST /refs` endpoint requires the body to be a **JSON array**, not an object. Using `ConvertTo-Json` on a single hashtable wraps it in an `{}` object, which the API rejects. Either manually construct the JSON string or wrap the hashtable in `@(...)` and verify the output is `[{...}]`.

    **Validate** that `$branchSha` is a real commit SHA (40 hex chars, not all zeros) before proceeding:
    ```powershell
    if (-not $branchSha -or $branchSha -eq "0000000000000000000000000000000000000000") {
        Write-Error "Branch SHA is null or all-zeros. Branch creation may have failed. Aborting."
        return
    }
    Write-Host "Branch SHA for push: $branchSha"
    ```

11. **Push the commit** to the branch. The `oldObjectId` in `refUpdates` MUST be `$branchSha` (which equals `$mainSha` for a newly created branch). This tells ADO to create a new commit whose **parent** is `$branchSha`, inheriting all existing files from that commit's tree:

    ```powershell
    $pushBody = @{
        refUpdates = @(
            @{
                name = "refs/heads/{user-alias}/{header}-update"
                oldObjectId = $branchSha   # MUST be a real SHA, never all-zeros
            }
        )
        commits = @(
            @{
                comment = "<generated commit message>"
                changes = $changes
            }
        )
    } | ConvertTo-Json -Depth 10

    $pushResult = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/pushes?api-version=7.0" -Method Post -Headers $headers -Body $pushBody
    ```

    > **Do NOT** combine branch creation and push into a single pushes API call. Always create the branch first (step 10), then push to it (step 11).

12. **Verify the push.** Confirm the new commit has a parent (is not orphaned) by checking the commit details:

    ```powershell
    $newCommitId = $pushResult.commits[0].commitId
    $commitDetail = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/commits/$newCommitId?api-version=7.0" -Headers $headers
    if (-not $commitDetail.parents -or $commitDetail.parents.Count -eq 0) {
        Write-Error "FATAL: Push created an orphan commit (no parent). The branch must be deleted and recreated. This means oldObjectId was wrong."
        # Clean up: delete the broken branch
        $deletePayload = "[{`"name`":`"refs/heads/{user-alias}/{header}-update`",`"oldObjectId`":`"$($commitDetail.commitId)`",`"newObjectId`":`"0000000000000000000000000000000000000000`"}]"
        Invoke-RestMethod -Uri "$adoBase/wdk-ddi/refs?api-version=7.0" -Method Post -Headers $headers -Body $deletePayload
        Write-Error "Broken branch deleted. Please retry the submission."
        return
    }
    Write-Host "Commit $newCommitId verified — parent: $($commitDetail.parents[0])"
    ```

13. **Create a pull request** targeting `main`:

    ```powershell
    $prBody = @{
        sourceRefName = "refs/heads/{user-alias}/{header}-update"
        targetRefName = "refs/heads/main"
        title = "{user-alias}/{header}-update: API reference docs for {header}.h"
        description = "<PR description with header name, API entity list, AI-assisted note>"
    } | ConvertTo-Json

    $prResult = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/pullrequests?api-version=7.0" -Method Post -Headers $headers -Body $prBody
    ```

    The PR description should include:
    - Header name documented
    - List of API entities with their types
    - Note that content was AI-assisted (`ai-usage: ai-assisted` metadata is set in each file)

14. **Display the PR URL** to the user:

    ```powershell
    $prUrl = "https://dev.azure.com/cpubwin/drivers/_git/wdk-ddi/pullrequest/$($prResult.pullRequestId)"
    Write-Host "PR created: $prUrl"
    ```

15. **Final summary.** Report:
    - Phase 1: Inventory — {N} APIs classified ({new} new, {update} updates)
    - Phase 2: Generate — {N} files written to `{outputDir}`
    - Phase 3: Submit — PR created at `{prUrl}`
    - Display "Workflow completed".
