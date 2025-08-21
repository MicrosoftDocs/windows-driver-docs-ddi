# Copilot Instructions for Windows Driver Docs DDI Repository

This repository contains the source files for the Windows Driver Kit (WDK) Device Driver Interface (DDI) reference documentation, published at [learn.microsoft.com/windows-hardware/drivers/ddi](/windows-hardware/drivers/ddi).

## Repository Structure

This repository contains over 25,000 markdown files documenting Windows driver APIs, organized in the `wdk-ddi-src/content/` directory. Each subdirectory represents a different driver technology area or header file.

## File Naming Conventions

The repository uses specific filename prefixes to indicate the type of documentation:

| Prefix | Type | Description | Example |
|--------|------|-------------|---------|
| **nf-** | Function | API functions and methods | `nf-ntifs-ccpreparemdlwrite.md` |
| **ns-** | Structure | Data structures and unions | `ns-ntifs-_file_full_dir_information.md` |
| **ne-** | Enum | Enumerations | `ne-wificx-wifi_adapter_tx_demux_type.md` |
| **nc-** | Callback | Callback functions and function pointers | `nc-wificx-evt_wifi_device_create_adapter.md` |
| **ni-** | IOCTL | I/O control codes | `ni-charging-ioctl_cad_disable_charging.md` |
| **nn-** | Interface | COM interfaces | `nn-printerextension-iprintschemadisplayableelement.md` |
| **nl-** | Class | C++ classes | `nl-engextcpp-extremotelist.md` |

## Content Structure

Each documentation file follows a standard structure:

### YAML Frontmatter
All files start with YAML metadata including:
- `UID`: Unique identifier for the API
- `title`: Display title with header file reference
- `description`: Brief description of the API
- `tech.root`: Technology area (e.g., netvista, ifsk, print, display)
- `ms.date`: Last update date
- Various `req.*` fields for requirements
- API metadata (`api_type`, `api_location`, `api_name`)
- Keywords and topic types

### Content Sections
Standard sections include:
- `## -description`: Detailed explanation
- `## -parameters` or `## -struct-fields`: Parameter/field details
- `## -return-value`: Return value information (for functions)
- `## -remarks`: Additional notes and usage guidance
- `## -see-also`: Related APIs and documentation

## AI Usage Metadata

When creating or significantly revising content using AI, you **must** include the `ai-usage` metadata attribute in the YAML frontmatter:

```yaml
ai-usage: ai-assisted  # or ai-generated
```

**AI Usage Values:**
- **`ai-assisted`**: Content created by a human author with AI help. A human reviewed and revised the content as needed.
- **`ai-generated`**: Content created by AI. A human author may have reviewed and revised the content as needed.

Including this metadata automatically adds a customer-facing AI disclosure to the published content.

## Link Format Requirements

**Important**: Do NOT use fully qualified links to learn.microsoft.com. Instead, use site-relative links:

❌ **Wrong**: `[Driver Development](/learn.microsoft.com/windows-hardware/drivers)`
✅ **Correct**: `[Driver Development](/windows-hardware/drivers)`

Examples:
- `/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparemdlwrite`
- `/windows-hardware/drivers/ifs/irp-mj-directory-control`
- `/windows/win32/secauthz/privilege-constants`

## Content Guidelines

### Writing Standards
1. **Accuracy**: Ensure all technical information is correct and up-to-date
2. **Consistency**: Follow existing patterns and terminology
3. **Clarity**: Write clear, concise descriptions that help developers
4. **Completeness**: Include all necessary details for proper API usage

### Cross-References
- Link to related APIs in the same technology area
- Reference prerequisite knowledge and setup requirements
- Include links to conceptual documentation where helpful

### Code Examples
- Use realistic, compilable code snippets when helpful
- Follow Windows driver coding standards
- Include proper error handling where applicable

## Technology Areas (tech.root)

Common technology areas include:
- `netvista`: Networking drivers
- `ifsk`: File system drivers  
- `print`: Printer drivers
- `display`: Display drivers
- `audio`: Audio drivers
- `kernel`: Kernel-mode APIs
- `IEEE`: IEEE 1394 drivers

## Metadata Requirements

Key metadata fields to include:
- **Required**: `UID`, `title`, `description`, `tech.root`, `ms.date`
- **API Info**: `api_type`, `api_location`, `api_name`  
- **Requirements**: `req.header`, `req.target-type`, `targetos`
- **Keywords**: `f1_keywords` for search optimization
- **AI Usage**: `ai-usage` when applicable

## Common Patterns

### Function Documentation
```markdown
## -description
Brief description of what the function does.

## -parameters
### -param ParameterName
Description of the parameter.

## -return-value
Description of return values and error codes.

## -remarks
Additional usage notes, restrictions, and context.

## -see-also
[Related API](related-api.md)
```

### Structure Documentation
```markdown
## -description
Description of the structure and its purpose.

## -struct-fields
### -field FieldName
Description of the field and its usage.

## -remarks  
Usage notes and alignment requirements.
```

## Best Practices

1. **Use existing patterns**: Review similar files for consistency
2. **Verify links**: Ensure all cross-references are valid
3. **Check metadata**: Validate all required YAML fields
4. **Test locally**: Verify markdown rendering if possible
5. **Follow naming**: Use the correct filename prefix for content type
6. **Include AI metadata**: Add `ai-usage` field when using AI assistance
7. **Use site-relative links**: Never use full learn.microsoft.com URLs

## Contributing Workflow

1. Follow the standard GitHub contribution workflow
2. Ensure your changes align with existing documentation patterns  
3. Include the `ai-usage` metadata when AI was used in content creation
4. Use site-relative links for all internal Microsoft documentation
5. Validate that filename prefixes match the content type
6. Review similar existing files to maintain consistency

For more detailed contribution guidelines, see [CONTRIBUTING.md](CONTRIBUTING.md).