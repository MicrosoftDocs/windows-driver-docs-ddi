---
mode: 'agent'
model: Claude Sonnet 4.5
tools: [microsoft_docs_search, runCommands, edit, runTasks]
description: 'Automated agent prompt that generates API reference pages for WDK DDI entities. It verifies access to git and the Learn MCP tool, reads the first attached CSV of target filenames, checks out corresponding stub files from origin/stubs/main, locates declarations and source code in attached headers and source files, uses existing repository reference pages as models, consults the Learn MCP server for supplemental information, and writes completed documentation pages. If git or Learn MCP access is unavailable, the agent reports the problem and stops.'
---

Prompt:

Your goal is to write API reference pages for Windows Driver Kit (WDK) entities such as functions, structures, enumerations, and so on.

1. Locate the first attachment whose filename ends with ".csv" and parse it as CSV (comma delimiter; first row = header; support quoted fields and embedded newlines). This .csv lists the target filenames for which you must write reference documentation.

2. Verify environment access:
    - Run `git status` to confirm Git is available in the terminal.
    - Verify access to the Learn MCP server (`microsoft.docs.mcp`).
    - If either check fails, stop and report the problem.

3. If the file exists, report it and don't check out its stub file. If the file doesn't exist, from the repository root, use the VS Code terminal window to check out its stub file with:
    `git checkout origin/stubs/main -- <path/filename.md>`

4. For each target file, use all of the following resources, if present, to gather context:
   - The attached header(s) that contain the entity's definition/declaration.
   - Any attached source code.
   - Any other attached files, such as specifications, meeting notes, etc.
   - The Learn MCP server for any supplemental information relevant to the entity being documented.
   - One or two existing completed reference pages in the repo for the same entity type to use as models. Use pages in the same header folder; otherwise use pages in a different folder.

5. Open and write the completed documentation pages in the files listed in the CSV, keeping the following guidelines in mind:
   - If the entity is an extended entity (ends in Ex or a number <n> or V<n>), use the content from the prior entity's file as a base, and then document the added extensions.
   - Keep your comments concise and relevant to developers. 
   - Don't generate repetitive information.
   - Don't include internal implementation details; focus on the public API and its usage.
   - Don't remove any existing text from the target files.

6. Ensure that `ai-usage: ai-assisted` is included as a metadata attribute in the YAML frontmatter. If this attribute is not present, add it.

7. Make the API entities in the -see-also section to relative links in markdown format. Write the -see-also section entries in alphabetical order.

8. Add or delete blank lines as needed to ensure there is only one blank line at the end of each file.

9. If a file matching `na-*.md` exists, rename that file to `index.md`.
