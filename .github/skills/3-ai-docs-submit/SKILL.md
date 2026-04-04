---
name: ai-docs-submit
description: 'Submit generated WDK DDI API reference documentation as a PR to the wdk-ddi repo. Use when: submitting docs, creating a PR for DDI docs, pushing documentation changes.'
argument-hint: 'Specify a header name (e.g. soundwireclass) and the path to the CSV file. The output\ subfolder next to the CSV must contain generated docs.'
---

# Submit DDI Docs

Submit generated API reference documentation as a pull request to the `wdk-ddi` Azure DevOps repo using the ADO REST API.

**No local repo clone required.** Branch creation, file push, and PR creation are all done via the ADO REST API.

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
| Source Branch | Auto-generated as `{user-alias}/{header}-update` (e.g. `brbenefield/soundwireclass-update`) |
| User Alias | Auto-detected from CSV `Owner` column, `$env:USERNAME`, or `az account show` |

## Prerequisites

- The output folder `{working_dir}\output\` must contain generated documentation files (from the `ai-docs-generate` skill).
- **Tip:** To run all three steps (inventory → generate → submit) with no interaction, use the `ai-docs-autopilot` skill instead.
- Azure CLI (`az`) should be available for auth token acquisition. If not, the agent will prompt for an ADO Personal Access Token (PAT) once per session (scope: Code Read+Write, Pull Request Contribute).

## Procedure

1. Strip the `.h` extension from the user-provided header name to get `{header}` (e.g. `soundwireclass.h` → `soundwireclass`).

2. **Resolve the user alias** for branch naming (`{user-alias}`). The alias identifies who is submitting the PR, not who owns the APIs. Try these sources in order and use the first non-empty value:
   a. The Windows username: `$env:USERNAME`.
   b. The Azure CLI identity: `az account show --query user.name -o tsv`, extracting the alias portion before `@`.

3. **Resolve paths.** The user provides the CSV path. Derive the working and output directories:

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
   - The target branch name: `{user-alias}/{header}-update`

   Prompt the user to confirm before proceeding.

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
15. Display **Workflow completed** confirming completion.

    ```
