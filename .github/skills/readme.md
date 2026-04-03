# AI-Docs API Documentation Workflow

Generate and publish API reference documentation for Windows Driver Kit (WDK) header files. The workflow inventories and verifies APIs from a user-created CSV, generates complete reference pages, and submits them as a pull request to the wdk-ddi Azure DevOps repo.

Run each step individually for interactive control, or use the autopilot skill to run all three unattended.

## Skills

The skills.md ([Claude Code skills](https://code.claude.com/docs/en/skills)) files for this workflow are located on the repo (and your local clone) in **\wdk-ddi\.github\skills**. 

| Skill | Description |
|-------|-------------|
| `ai-docs-inventory` | Classify APIs in a CSV against existing docs, stubs, and published content. Outputs an updated CSV with status (new / update) for each entry. |
| `ai-docs-generate` | Generate documentation pages from stub files, OS source declarations, and published docs. Writes completed .md files to an output folder for user review. |
| `ai-docs-submit` | Push generated docs to a new branch in the wdk-ddi repo and create a pull request targeting the main branch. |
| `ai-docs-autopilot` | Run all three steps end-to-end with no interaction. Stops only on error. Requires auto-pilot mode. |

## Prerequisites

### VS Code with GitHub Copilot Chat

The skills are invoked as Copilot agent commands inside VS Code.

- Install from the Microsoft internal package manager or the [VS Code internal release site](https://aka.ms/vscode-insider-install). Ensure the **GitHub Copilot Chat** extension is installed and signed in.

### Azure CLI (az)

Used to acquire an Azure DevOps bearer token. Run `az login` once before starting the workflow. If az is unavailable, you will be prompted for an ADO Personal Access Token (PAT).

- Install from the [Azure CLI internal install page](https://aka.ms/installazurecliwindows) or via winget:
    ```powershell
    winget install Microsoft.AzureCLI
    ```
    After installation, authenticate once:
    ```powershell
    az login
    ```

### MCP Servers

| Server | Required | Purpose |
|--------|----------|---------|
| `substrate-mcp` | Yes | Retrieves OS source code declarations |
| `microsoft.docs` | No (recommended) | Searches published Microsoft Learn docs for supplemental context |

- Add the following entries to your VS Code MCP configuration file (`%APPDATA%\Code\User\mcp.json`). If the file does not exist, create it with the full JSON below. If it already exists, merge the `servers` entries.

    ```json
    {
      "servers": {
        "microsoft.docs.mcp": {
          "type": "http",
          "url": "https://learn.microsoft.com/api/mcp"
        },
        "substrate-mcp-mini": {
          "url": "https://mcp.engcopilot.net",
          "type": "http",
          "headers": {
            "x-mcp-ec-organization": "microsoft",
            "x-mcp-ec-project": "OS",
            "x-mcp-ec-repository": "os.2020",
            "x-mcp-ec-branch": "official/main"
          }
        }
      }
    }
    ```

Restart VS Code after editing `mcp.json` for the servers to become available.

### CSV File

A user-created CSV listing the APIs to document, typically exported from the Meriwether report. Must contain a column with file paths such as:

```
wdk-ddi-src/content/{header}/nf-{header}-funcname.md
```

## Azure DevOps Permissions

Your identity (or PAT) needs these permissions in the **cpubwin/drivers** ADO project:

| Repo | Permission | Purpose |
|------|-----------|---------|
| `wdk-ddi` | Code: Read | Read stubs, existing docs, and repo refs |
| `wdk-ddi` | Code: Contribute | Push commits to `ai-doc/*` working branches |
| `wdk-ddi` | Pull Requests: Contribute | Create pull requests |
| `wdk-ddi-build` | Code: Read | Check published docs on the live branch |
| `windows-driver-docs-ddi` | Code: Read | Check staging branch for index.md existence |

> [!NOTE]
> If using a PAT instead of Azure CLI for auth, set the scope to **Code (Read & Write)** and **Pull Request Threads (Read & Write)** at minimum.

## Step 1: Prep

1. Update your local repo clone from *wdk-ddi/main*.
1. Create a local working project folder, for example *C:\ai-docs\\\{header-name}*. 
1. In Meriwether, filter your view to the header you want to update, for example *State=New* and *Header={header-name}*.
1. Select the three dot **More options** menu to the right of the filtered list, select **Export data** -> **Data with current layout** -> **Export**.  
1. Save the file as a .csv file in your project folder, for example *C:\ai-docs\\\{header-name}\\\{header-name}.csv*.
1. In VS Code, select **Open Workspace from file**, navigate to your local clone, and select **\wdk-ddi\ai-docs.code-workspace**.

> [!NOTE]
> I've tested this successfully with sets of 10 new APIs and am currently running larger jobs to find an acceptable upper limit on the number of files it can handle. 


## Step 2: Run the workflow

### Interactive method (to review each phase)

Each command is typed in the Copilot Chat panel:

**1. Inventory**

```
/ai-docs-inventory {header} {path\to\header.csv}
```

Reviews the CSV, queries ADO for stub/doc status on each API, classifies entries, and rewrites the CSV with filename + status. Opens the CSV for review and asks whether to continue.

**2. Generate**

```
/ai-docs-generate {header} {path\to\header.csv}
```

Reads the CSV, fetches stubs or existing docs from ADO, retrieves source declarations via substrate-mcp, and writes completed .md files to an `output\` subfolder under your project folder for review. Displays a summary and prompts to submit the PR.

**3. Submit**

```
/ai-docs-submit {header} {path\to\header.csv}
```

Reads the new docs in the `output\` folder, creates or reuses an `ai-doc/{header}-update` branch, pushes a commit with all generated files, and opens a pull request targeting main. Displays the PR URL and summary.

### Autopilot method (no user interaction)

```
/ai-docs-autopilot {header} {path\to\header.csv}
```

Runs inventory, generate, and submit in sequence. No prompts between steps. The process stops only if an error is encountered.

> [!NOTE]
> To enable autopilot mode in VS Code, select **Autopilot (Preview)** from the **Set permissions** selector directly below the chat window.  You can also run the command from a Copilot CLI window in autopilot mode.

## Output Locations

| Path | Contents |
|------|----------|
| `{csv_folder}\` | Working directory (derived from CSV path) |
| `{csv_folder}\output\` | Generated .md files |
| `{csv_folder}\inventory.ps1` | Inventory script (auto-generated) |


Troubleshooting
---------------

  "Failed to get ADO token"
      Run "az login" in a terminal, then retry.

  "No generated docs found in output\"
      The generate step did not produce files. Check for errors in the
      Copilot Chat output and verify substrate-mcp is accessible.

  Orphan commit / PR shows all files deleted
      The submit step includes safeguards against this. If it occurs,
      the broken branch is automatically deleted. Retry the submit.

  "Stub not found" for an API
      The stub does not exist on the stubs/main branch. Verify the
      header was processed by the stub generation pipeline.
