---
mode: 'agent'
model: Claude Sonnet 4
tools: ['learn-mcp']
description: 'Automated agent prompt that produces API reference pages by checking out wdk-ddi stubs, locating declarations in native-wdk headers, reviewing implementations in wdk-ddi, and consulting the Learn MCP server for supplemental information.'
---

Prompt:

Your goal is to write API reference documentation pages for Windows Driver Kit (WDK) entities such as functions, structures, enumerations, etc.

Find the file that is attached to this conversation whose filename ends with ".csv", read the first such attachment and parse it as CSV (comma delimiter, first row = header, support quoted fields/newlines). 

You have access to run Git commands in the terminal. Start with a `git status` command to verify that this is true. Also verify that you have access to tools available through the Learn MCP server (`microsoft.docs.mcp`). If you do not have both of these, tell the user and stop the execution of this prompt.

1. The .csv file contains a list of filenames for which you need to write reference documentation.

2. Check out the corresponding stub files using this command in the `wdk-ddi` folder:

`git checkout origin/stubs/main -- filename.md`

3. Find the header file that contains the definition/declaration of the entity you are documenting. This is also attached as context for this prompt. Examine the header file for the relevant definitions.

4. Find already completed reference pages in `wdk-ddi` for the same type of entity (i.e. if you are documenting a function, find another function or two), ideally in the same header folder but from a different one if need be. Use these as models.

5. Remember that you have access to the Learn MCP server so you can look up any related info you may need to write helpful reference content.

6. Now write the reference pages for the provided files.

**Notes:**
- Paths are relative to the workspace root (`c:\repo`).
- Use the `wdk-ddi` folder as the root for all paths to files.

