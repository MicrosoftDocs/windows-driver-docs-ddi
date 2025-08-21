# Windows Driver Documentation DDI - Copilot Instructions

## Repository Overview

This repository contains the source files for the Windows Driver Kit (WDK) Device Driver Interface (DDI) reference documentation. The content is published to [learn.microsoft.com/windows-hardware/drivers/ddi](/windows-hardware/drivers/ddi).

### Purpose
- Provides comprehensive API reference documentation for Windows device drivers
- Covers functions, structures, enumerations, IOCTLs, callbacks, interfaces, and classes
- Serves as the authoritative source for driver development APIs across hundreds of driver categories

## Repository Structure

```
windows-driver-docs-ddi/
├── wdk-ddi-src/content/          # Main content directory
│   ├── {category}/               # Driver category directories (e.g., wificx, ntddk, etc.)
│   │   ├── nf-{category}-*.md   # Function documentation
│   │   ├── ns-{category}-*.md   # Structure documentation  
│   │   ├── ne-{category}-*.md   # Enumeration documentation
│   │   ├── ni-{category}-*.md   # IOCTL documentation
│   │   ├── nc-{category}-*.md   # Callback documentation
│   │   ├── nn-{category}-*.md   # Interface documentation
│   │   ├── nl-{category}-*.md   # Class documentation
│   │   └── index.yml            # Category index
│   └── docfx.json               # Build configuration
├── CONTRIBUTING.md              # Contribution guidelines
└── README.md                    # Repository information
```

## File Naming Conventions

All documentation files follow a strict naming pattern using prefixes to indicate the type of API element:

### Filename Prefix Key

| Prefix | Type | Description | Example |
|--------|------|-------------|---------|
| `ne` | Enum | Enumerations and enumerated types | `ne-wificx-wifi_adapter_type.md` |
| `nc` | Callback | Callback functions and function pointers | `nc-wificx-evt_wifi_device_create_adapter.md` |
| `ni` | IOCTL | Input/Output Control codes | `ni-charging-ioctl_cad_disable_charging.md` |
| `ns` | Structure | Data structures and unions | `ns-wificx-wifi_device_config.md` |
| `nl` | Class | Classes (primarily for C++ APIs) | `nl-engextcpp-extremotedata.md` |
| `nn` | Interface | COM interfaces and abstract base classes | `nn-{category}-{interface_name}.md` |
| `nf` | Function | Functions and methods | `nf-wificx-wifideviceinitialize.md` |

### Naming Pattern
Files should follow the pattern: `{prefix}-{category}-{api_name}.md`

Where:
- `{prefix}` is one of the prefixes above
- `{category}` matches the directory name
- `{api_name}` is the lowercase, hyphenated version of the API name

## Content Structure

Each documentation file contains:

### YAML Frontmatter (Required)
Every file must start with YAML frontmatter containing metadata:

```yaml
---
UID: {Unique identifier}
title: {API Name} ({header file})
description: {Brief description of the API}
tech.root: {Technology area}
ms.date: {Date in MM/DD/YYYY format}
targetos: Windows
keywords: ["{API Name}"]
ms.keywords: {Comma-separated keywords}
req.header: {Header file name}
req.include-header: {Include header if different}
req.target-type: {Target type}
req.target-min-winverclnt: {Minimum Windows client version}
req.target-min-winversvr: {Minimum Windows server version}
req.lib: {Required library}
req.dll: {Required DLL}
req.irql: {IRQL level}
req.ddi-compliance: {DDI compliance info}
topic_type:
 - apiref
api_type:
 - {HeaderDef|DllExport|LibDef}
api_location:
 - {header file or library}
api_name:
 - {API name}
f1_keywords:
 - {API name}
 - {header}/{API name}
dev_langs:
 - c++
ai-usage: {ai-assisted|ai-generated}
---
```

### Required AI Usage Metadata
**IMPORTANT**: All articles created or revised using AI must include the `ai-usage` metadata attribute in the YAML frontmatter.

- `ai-assisted`: Content was created by a human author with the help of AI. A human author reviewed and revised the content as needed.
- `ai-generated`: Content was created by AI. A human author may have reviewed and revised the content as needed.

This metadata automatically adds a customer-facing AI disclosure to the published content.

### Common Metadata Patterns

#### API Types by Prefix:
- **Enumerations (ne)**: `req.construct-type: enumeration`
- **Callbacks (nc)**: `req.construct-type: function` 
- **IOCTLs (ni)**: `api_type: HeaderDef`
- **Structures (ns)**: `req.construct-type: structure`
- **Classes (nl)**: `api_type: HeaderDef` or `LibDef`
- **Interfaces (nn)**: `api_type: HeaderDef`
- **Functions (nf)**: `api_type: DllExport` or `HeaderDef`

#### Technology Roots (tech.root):
Common values include: `netvista`, `ifsk`, `kernel`, `audio`, `display`, `image`, `battery`, etc.

#### Version Requirements:
- Use specific Windows versions: `Windows 11`, `Windows 10, version 1903`, etc.
- Server versions: `Windows Server 2022`, `Windows Server 2019`, etc.

### Content Sections

#### Standard Sections (in order):
1. `## -description` - Detailed description of the API
2. `## -parameters` (functions/methods only) - Parameter descriptions
3. `## -struct-fields` (structures only) - Field descriptions  
4. `## -enum-fields` (enumerations only) - Enumeration value descriptions
5. `## -returns` (functions with return values) - Return value information
6. `## -remarks` - Additional usage notes, examples, and important information
7. `## -see-also` - Related API references

#### Special Section Types:
- `## -ioctlparameters` - For IOCTL documentation (ni- files)
- `## -syntax` - Function/method syntax (automatically generated, do not edit)
- `## -inheritance` - For interface/class inheritance (nn-/nl- files)

#### Parameter/Field Format:
```markdown
### -param ParameterName
Brief description of the parameter.

### -field FieldName  
Brief description of the field.

### -field EnumValue:ValueNumber
Brief description of the enumeration value.
```

## Link Formatting Guidelines

### Site-Relative Links (Required)
**IMPORTANT**: Use site-relative links instead of fully qualified URLs for learn.microsoft.com content.

✅ **Correct:**
```markdown
[Windows Hardware Developer](/windows-hardware)
[Driver Development](/windows-hardware/drivers)
[API Reference](/windows-hardware/drivers/ddi)
```

❌ **Incorrect:**
```markdown  
[Windows Hardware Developer](https://learn.microsoft.com/windows-hardware)
[Driver Development](https://learn.microsoft.com/windows-hardware/drivers)
[API Reference](https://learn.microsoft.com/windows-hardware/drivers/ddi)
```

### Cross-References
- Link to other APIs using relative paths: `[OtherFunction](nf-category-otherfunction.md)`
- Link to structures/enums: `[STRUCTURE_NAME](ns-category-structure_name.md)`
- Use **bold** formatting for API names in text: `**ApiName**`

### External Links
External links (non-learn.microsoft.com) should use full URLs:
```markdown
[Windows SDK](https://developer.microsoft.com/windows/downloads/windows-sdk/)
```

## Writing Guidelines

### Style and Tone
- Use clear, concise technical language
- Write in third person
- Use active voice when possible
- Be consistent with terminology across related APIs

### Content Quality
- Ensure all parameters/fields are documented
- Include practical usage examples in -remarks when helpful
- Cross-reference related APIs in -see-also sections
- Verify technical accuracy of all information
- Follow Microsoft Writing Style Guide for technical documentation
- Use consistent terminology with existing documentation

### Code Examples
When including code examples:
- Use proper C/C++ syntax highlighting
- Include necessary header files
- Provide context for when/why the code would be used
- Keep examples concise but complete

```cpp
// Example code block
#include <wificx.h>

NTSTATUS
EvtWifiDeviceCreateAdapter(
    _In_ WDFDEVICE Device,
    _Inout_ WIFI_ADAPTER_INIT* AdapterInit
    )
{
    // Implementation here
    return STATUS_SUCCESS;
}
```

### Common Patterns
- Functions: Focus on purpose, parameters, return values, and usage patterns
- Structures: Document each field, memory layout considerations, and usage context
- Enumerations: Explain each value and when it's used
- IOCTLs: Include input/output buffer descriptions and operation details

## Build and Validation

The repository uses DocFX for building documentation. Key configuration is in `docfx.json`.

### Local Validation
- Ensure YAML frontmatter is valid
- Verify all internal links resolve correctly
- Check that filename conventions are followed
- Validate that required metadata is present

### Content Review Checklist
- [ ] Correct filename prefix used (ne/nc/ni/ns/nl/nn)
- [ ] YAML frontmatter complete and valid
- [ ] AI usage metadata included if AI was used
- [ ] Site-relative links used for learn.microsoft.com content
- [ ] All required sections present (-description, -parameters/-struct-fields/-enum-fields as appropriate, -remarks, -see-also)
- [ ] Technical accuracy verified
- [ ] Cross-references added to related APIs
- [ ] Examples provided where helpful
- [ ] Consistent with Microsoft Writing Style Guide
- [ ] All parameters/fields documented completely

## Categories and Technology Areas

The repository covers numerous driver categories including but not limited to:
- Audio (acx*, dmusicks, dmusprop, hdaudio, etc.)
- Display (d3d*, dispmprt, video, etc.)
- Network (ndis*, net*, wifi*, etc.)
- Storage (storage*, scsi*, ata, etc.)  
- USB (usb*, ucm*, etc.)
- Sensors (sensors*, gnss*, etc.)
- And many more specialized driver areas

Each category has its own directory structure and may have category-specific conventions documented in local README files.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed contribution guidelines, including:
- Pull request process
- Code review requirements  
- Microsoft Contributor License Agreement (CLA)
- Style guide adherence

For questions or issues, create an issue in this repository or contact the Windows driver documentation team.