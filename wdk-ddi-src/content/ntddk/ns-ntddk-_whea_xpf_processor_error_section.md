---
UID: NS:ntddk._WHEA_XPF_PROCESSOR_ERROR_SECTION
title: _WHEA_XPF_PROCESSOR_ERROR_SECTION (ntddk.h)
description: The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes processor error data that is specific to the x86/x64 processor architecture.
old-location: whea\whea_xpf_processor_error_section.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["WHEA_XPF_PROCESSOR_ERROR_SECTION structure"]
ms.keywords: "*PWHEA_XPF_PROCESSOR_ERROR_SECTION, PWHEA_XPF_PROCESSOR_ERROR_SECTION, PWHEA_XPF_PROCESSOR_ERROR_SECTION structure pointer [WHEA Drivers and Applications], WHEA_XPF_PROCESSOR_ERROR_SECTION, WHEA_XPF_PROCESSOR_ERROR_SECTION structure [WHEA Drivers and Applications], _WHEA_XPF_PROCESSOR_ERROR_SECTION, ntddk/PWHEA_XPF_PROCESSOR_ERROR_SECTION, ntddk/WHEA_XPF_PROCESSOR_ERROR_SECTION, whea.whea_xpf_processor_error_section, whearef_e3338334-dc16-4242-9c30-0daaab2df957.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WHEA_XPF_PROCESSOR_ERROR_SECTION, *PWHEA_XPF_PROCESSOR_ERROR_SECTION
ms.custom: 19H1
f1_keywords:
 - _WHEA_XPF_PROCESSOR_ERROR_SECTION
 - ntddk/_WHEA_XPF_PROCESSOR_ERROR_SECTION
 - PWHEA_XPF_PROCESSOR_ERROR_SECTION
 - ntddk/PWHEA_XPF_PROCESSOR_ERROR_SECTION
 - WHEA_XPF_PROCESSOR_ERROR_SECTION
 - ntddk/WHEA_XPF_PROCESSOR_ERROR_SECTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_XPF_PROCESSOR_ERROR_SECTION
 - PWHEA_XPF_PROCESSOR_ERROR_SECTION
 - WHEA_XPF_PROCESSOR_ERROR_SECTION
---

# _WHEA_XPF_PROCESSOR_ERROR_SECTION structure


## -description

The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes processor error data that is specific to the x86/x64 processor architecture.

## -struct-fields

### -field ValidBits

A [WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS](./ns-ntddk-_whea_xpf_processor_error_section_validbits.md) union that specifies which members of this structure contain valid data and the number of structures that are contained in the <b>VariableInfo</b> member.

### -field LocalAPICId

The value programmed into the local APIC ID register.

This member contains valid data only if the <b>ValidBits.LocalAPICId</b> bit is set.

### -field CpuId

A 48-byte buffer that contains the results of executing the CPUID instruction. For more information about the CPUID instruction, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.

This member contains valid data only if the <b>ValidBits.CpuId </b>bit is set.

### -field VariableInfo

A variable length buffer that contains zero or more [WHEA_XPF_PROCINFO](./ns-ntddk-_whea_xpf_procinfo.md) structures followed by zero or more [WHEA_XPF_CONTEXT_INFO](./ns-ntddk-_whea_xpf_context_info.md) structures. The number of WHEA_XPF_PROCINFO structures is specified in <b>ValidBits.ProcInfoCount</b>. The number of WHEA_XPF_CONTEXT_INFO structures is specified in <b>ValidBits.ContextInfoCount</b>. For a diagram that shows how these data structures are stored in the buffer, see the Remarks section.

## -remarks

The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes the error data that is contained in an x86/x64 processor error section of an [error record](/windows-hardware/drivers/whea/error-records). An error record contains an x86/x64 processor error section only if the <b>SectionType </b>member of one of the [WHEA_ERROR_RECORD_SECTION_DESCRIPTOR](./ns-ntddk-_whea_error_record_section_descriptor.md) structures that describes the error record sections for that error record contains XPF_PROCESSOR_ERROR_SECTION_GUID.

The following diagram shows how the data structures that contain the processor error data are stored in the <b>VariableInfo</b> member.
<img alt="Diagram illustrating how the data structures that contain the processor error data are stored in the VariableInfo member" src="images/wheaxpfsection.png"/>

## -see-also

- [WHEA_ERROR_RECORD_SECTION_DESCRIPTOR](./ns-ntddk-_whea_error_record_section_descriptor.md)
- [WHEA_XPF_CONTEXT_INFO](./ns-ntddk-_whea_xpf_context_info.md)
- [WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS](./ns-ntddk-_whea_xpf_processor_error_section_validbits.md)
- [WHEA_XPF_PROCINFO](./ns-ntddk-_whea_xpf_procinfo.md)

