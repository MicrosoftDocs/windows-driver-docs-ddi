---
mode: 'agent'
model: Claude Sonnet 4
tools: ['learn-mcp']
description: 'Automated agent prompt that generates API reference pages for WDK DDI entities. It verifies access to git and the Learn MCP tool, reads the first attached CSV of target filenames, checks out corresponding stub files from origin/stubs/main, locates declarations in attached headers, uses existing repository reference pages as models, consults the Learn MCP server for supplemental information, and writes completed documentation pages. If git or Learn MCP access is unavailable, the agent reports the problem and stops.'
---

Prompt:

Your goal is to write API reference documentation pages for Windows Driver Kit (WDK) entities such as functions, structures, enumerations, etc.

1. Locate the first attachment whose filename ends with ".csv" and parse it as CSV (comma delimiter; first row = header; support quoted fields and embedded newlines).

2. Verify environment access:
    - Run `git status` to confirm Git is available in the terminal.
    - Verify access to the Learn MCP server (`microsoft.docs.mcp`).
    - If either check fails, report the problem to the user and stop.

3. The .csv lists the target filenames for which you must write reference documentation.

4. From the repository root, check out each corresponding stub file with:
    `git checkout origin/stubs/main -- <path/filename.md>`

5. For each target file:
    - Locate the attached header that contains the entity's definition/declaration and examine it for relevant definitions.
    - Find one or two existing completed reference pages in the repo for the same entity type (preferably in the same header folder; otherwise use a different one) and use them as models.

6. Use the Learn MCP server for any supplemental information needed.

7. Write the completed documentation pages for the files listed in the CSV.

