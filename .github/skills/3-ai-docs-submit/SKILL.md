---
name: ai-docs-submit
description: 'Submit generated WDK DDI API reference documentation as a PR to the wdk-ddi repo. Use when: submitting docs, creating a PR for DDI docs, pushing documentation changes.'
argument-hint: 'Specify a header name (e.g. soundwireclass) and the path to the CSV file. The output\ subfolder next to the CSV must contain generated docs.'
---

# Submit DDI Docs

Submit generated API reference documentation as a pull request to the `wdk-ddi` Azure DevOps repo using the ADO REST API.

**No local repo clone required.** Branch creation, file push, and PR creation are all done via a single atomic REST API call.

## Parameters

| Parameter | Value |
|-----------|-------|
| Header Name | Provided by the user (e.g. `soundwireclass`) |
| CSV Path | Provided by the user at any local path |
| Working Directory | Derived from CSV path (parent folder of the CSV file) |
| Output Directory | `{working_dir}\output\` |
| ADO Org | `https://dev.azure.com/cpubwin` |
| ADO Project | `drivers` |
| Docs Repo | `wdk-ddi` |
| Target Branch | `main` |
| Source Branch | Auto-generated as `ai-doc/{header}-update` (e.g. `ai-doc/soundwireclass-update`) |

## Prerequisites

- The output folder `{working_dir}\output\` must contain generated documentation files (from the `ai-docs-generate` skill).
- Azure CLI (`az`) should be available for auth token acquisition. If not, the agent will prompt for an ADO Personal Access Token (PAT) once per session (scope: Code Read+Write, Pull Request Contribute).

## Procedure

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

   If the CSV does not exist, inform the user and stop. Use the CSV entries to identify the API entities for the commit message and PR description.

3. Verify the output directory exists and contains files:

   ```powershell
   $outputFiles = Get-ChildItem -Path $outputDir -Filter "*.md" -ErrorAction SilentlyContinue
   if (-not $outputFiles -or $outputFiles.Count -eq 0) {
       Write-Error "No generated docs found in $outputDir. Run ai-docs-generate first."
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

9. **Pause for human review.** Display:
   - List of files to be pushed with their change types (`add` / `edit`)
   - Total file count
   - The generated commit message
   - The target branch name: `ai-doc/{header}-update`

   Prompt the user to confirm before proceeding.

10. **Atomic push: create branch + commit all files** in a single REST API call:

    ```powershell
    $pushBody = @{
        refUpdates = @(
            @{
                name = "refs/heads/ai-doc/{header}-update"
                oldObjectId = "0000000000000000000000000000000000000000"
            }
        )
        commits = @(
            @{
                comment = "<generated commit message>"
                changes = $changes
                newBranch = @{
                    name = "refs/heads/main"
                    objectId = $mainSha
                }
            }
        )
    } | ConvertTo-Json -Depth 10

    $pushResult = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/pushes?api-version=7.0" -Method Post -Headers $headers -Body $pushBody
    ```

    Note: If the branch `ai-doc/{header}-update` already exists, the push will fail. In that case, first get the branch's current SHA and use it as the `oldObjectId` instead of all-zeros:
    ```powershell
    $branchRef = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/refs?filter=heads/ai-doc/{header}-update&api-version=7.0" -Headers $headers
    if ($branchRef.value.Count -gt 0) {
        # Branch exists — use its SHA as oldObjectId for an update push
        $oldObjectId = $branchRef.value[0].objectId
    }
    ```

11. **Create a pull request** targeting `main`:

    ```powershell
    $prBody = @{
        sourceRefName = "refs/heads/ai-doc/{header}-update"
        targetRefName = "refs/heads/main"
        title = "ai-doc/{header}-update: API reference docs for {header}.h"
        description = "<PR description with header name, API entity list, AI-assisted note>"
    } | ConvertTo-Json

    $prResult = Invoke-RestMethod -Uri "$adoBase/wdk-ddi/pullrequests?api-version=7.0" -Method Post -Headers $headers -Body $prBody
    ```

    The PR description should include:
    - Header name documented
    - List of API entities with their types
    - Note that content was AI-assisted (`ai-usage: ai-assisted` metadata is set in each file)

12. **Display the PR URL** to the user:

    ```powershell
    $prUrl = "https://dev.azure.com/cpubwin/drivers/_git/wdk-ddi/pullrequest/$($prResult.pullRequestId)"
    Write-Host "PR created: $prUrl"
    ```
