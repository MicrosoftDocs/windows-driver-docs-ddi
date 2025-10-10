---
mode: 'agent'
model: Claude Sonnet 4
tools: [microsoft_docs_search, runCommands, edit, runTasks]
description: 'Automated agent prompt that generates API reference pages for WDK DDI entities. It verifies access to git and the Learn MCP tool, reads the first attached CSV of target filenames, checks out corresponding stub files from origin/stubs/main, locates declarations in attached headers, uses existing repository reference pages as models, consults the Learn MCP server for supplemental information, and writes completed documentation pages. If git or Learn MCP access is unavailable, the agent reports the problem and stops.'
---

Prompt:

Your goal is to write API reference documentation pages for Windows Driver Kit (WDK) entities such as functions, structures, enumerations, and so on.

1. Locate the first attachment whose filename ends with ".csv" and parse it as CSV (comma delimiter; first row = header; support quoted fields and embedded newlines).

2. Verify environment access:
    - Run `git status` to confirm Git is available in the terminal.
    - Verify access to the Learn MCP server (`microsoft.docs.mcp`).
    - If either check fails, stop and report the problem to the user.

3. The .csv lists the target filenames for which you must write reference documentation.

4. From the repository root, use the VS Code terminal window to check out each corresponding stub file with:
    `git checkout origin/stubs/main -- <path/filename.md>`

5. For each target file:
   - Locate the attached header that contains the entity's definition/declaration and examine it for relevant definitions.
   - Find one or two existing completed reference pages in the repo for the same entity type (preferably in the same header folder; otherwise use a different one) and use them as models.

6. If there is source code included as context, review for use cases.

7. If there is a specification file included as context, use it for details.

8. Use the Learn MCP server for any supplemental information needed.

9. Open and write the completed documentation pages in the checked out files listed in the CSV.

10. Don't remove anything from the stub files. If no information exists for a field or entity, leave it blank and move on.

11. Ensure that `ai-usage: ai-assisted` is included as a metadata attribute in the YAML frontmatter. If this attribute is not present, add it.

12. Make the API entities in the -see-also section to relative links in markdown format. Arrange the -see-also section a dashed list of bulleted links.

13. Add or delete blank lines as needed to ensure there is only one blank line at the end of each file.

14. If a file matching `na-*.md` exists, rename that file to `index.md`
