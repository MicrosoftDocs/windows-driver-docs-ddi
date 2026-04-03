---
name: ai-docs-inventory
description: 'Inventory and classify APIs listed in a pre-provided CSV for a WDK header file. Use when: inventorying a header, classifying APIs, validating a CSV for doc generation, checking what needs to be documented.'
argument-hint: 'Specify a header name (e.g. soundwireclass) and the path to the CSV file.'
---

# Inventory Header

Read a pre-provided CSV of target API filenames, cross-reference each entry against existing docs, stubs, and published content via the ADO REST API, classify their status, and finalize the CSV for use with the `ai-docs-generate` skill.

**No local repo clones required.** All repo interactions use the Azure DevOps REST API.

## Parameters

| Parameter | Value |
|-----------|-------|
| ADO Org | `https://dev.azure.com/cpubwin` |
| ADO Project | `drivers` |
| Docs Repo | `wdk-ddi` (branches: `main`, `stubs/main`) |
| Published Docs Repo | `wdk-ddi-build` (branch: `live`) |
| Content Path | `wdk-ddi-src/content/{header}/` |
| Stubs Branch | `stubs/main` (default; user may specify alternate like `stubs/release-amethyst`) |
| Header Name | Provided by the user (e.g. `soundwireclass`) |
| CSV Input | Provided by the user at any local path (e.g. `D:\work\soundwireclass.csv`) |
| Working Directory | Derived from CSV path (parent folder of the CSV file) |

## Prerequisites

- The user provides a header name and a path to a CSV file. **That is the only user requirement.**
- Azure CLI (`az`) should be available for auth token acquisition. If not, the agent will prompt for an ADO Personal Access Token (PAT) once per session.

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
1. Create a script file at `{workingDir}\inventory.ps1` containing all the logic from the Procedure below.
2. Execute it in a single terminal call: `powershell -ExecutionPolicy Bypass -File "{workingDir}\inventory.ps1"`
3. Parse the script's console output to present results to the user.

The script should accept no parameters — hardcode the `{header}`, `{csvPath}`, and `{workingDir}` values directly into the generated script.

## Procedure

Write a single `inventory.ps1` script that performs all of the following steps, then execute it.

1. Strip the `.h` extension from the user-provided header name to get `{header}` (e.g. `soundwireclass.h` → `soundwireclass`).

2. **Resolve paths.** The user provides a CSV path. Derive the working directory from it. The script should validate the CSV exists and read it:

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

9. **Write the updated CSV** at the original CSV path. The format must be compatible with the `ai-docs-generate` skill:

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

After the script finishes, the agent should:

11. Open the CSV in the editor:

    ```powershell
    code $csvPath
    ```

12. **Continue or stop.** Ask the user:

    > Inventory complete. Press **y** to continue to generate API docs, or type **n** to stop.

    - If the user types **y**: automatically invoke the `ai-docs-generate` skill, passing the same header name and CSV path. Behave as if the user typed `/ai-docs-generate {header}.h {workingDir}`.
    - If the user types **n**: stop and tell them they can run it later with: `/ai-docs-generate {header}.h {workingDir}`

    > **Tip:** To run all three steps (inventory → generate → submit) with no interaction, use the `ai-docs-autopilot` skill instead.

