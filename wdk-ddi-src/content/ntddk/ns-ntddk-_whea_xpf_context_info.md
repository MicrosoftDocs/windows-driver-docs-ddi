---
UID: NS:ntddk._WHEA_XPF_CONTEXT_INFO
title: _WHEA_XPF_CONTEXT_INFO (ntddk.h)
description: The WHEA_XPF_CONTEXT_INFO structure describes processor context information for an x86 or x64 processor.
tech.root: whea
ms.date: 03/14/2023
keywords: ["WHEA_XPF_CONTEXT_INFO structure"]
ms.keywords: "*PWHEA_XPF_CONTEXT_INFO, PWHEA_XPF_CONTEXT_INFO, PWHEA_XPF_CONTEXT_INFO structure pointer [WHEA Drivers and Applications], WHEA_XPF_CONTEXT_INFO, WHEA_XPF_CONTEXT_INFO structure [WHEA Drivers and Applications], _WHEA_XPF_CONTEXT_INFO, ntddk/PWHEA_XPF_CONTEXT_INFO, ntddk/WHEA_XPF_CONTEXT_INFO, whea.whea_xpf_context_info, whearef_3e1bae81-9b21-4b0c-bd86-b957afb95713.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt:
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
req.typenames: WHEA_XPF_CONTEXT_INFO, *PWHEA_XPF_CONTEXT_INFO
f1_keywords:
 - _WHEA_XPF_CONTEXT_INFO
 - ntddk/_WHEA_XPF_CONTEXT_INFO
 - PWHEA_XPF_CONTEXT_INFO
 - ntddk/PWHEA_XPF_CONTEXT_INFO
 - WHEA_XPF_CONTEXT_INFO
 - ntddk/WHEA_XPF_CONTEXT_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_XPF_CONTEXT_INFO
 - PWHEA_XPF_CONTEXT_INFO
 - WHEA_XPF_CONTEXT_INFO
---

## -description

The **WHEA_XPF_CONTEXT_INFO** structure describes processor context information for an x86 or x64 processor.

## -struct-fields

### -field RegisterContextType

The type of processor context information described by the structure. Possible values are:

|Value  |Description  |
|---------|---------|
|XPF_CONTEXT_INFO_UNCLASSIFIEDDATA     |    The buffer contains raw unformatted data. The number of bytes of data is specified in the RegisterDataSize member.     |
|XPF_CONTEXT_INFO_MSRREGISTERS     |    The buffer contains an array of 64-bit machine check and other machine-specific registers. The number of registers in the array is determined by dividing the size specified in the RegisterDataSize member by eight.     |
| XPF_CONTEXT_INFO_32BITCONTEXT  | 32-bit execution context registers. The buffer contains a WHEA_X86_REGISTER_STATE structure.  |
|  XPF_CONTEXT_INFO_64BITCONTEXT | 64-bit execution context registers. The buffer contains a WHEA_X64_REGISTER_STATE structure. |
| XPF_CONTEXT_INFO_FXSAVE  |  The buffer contains the floating point registers as saved by the FXSAVE instruction. For more information about the FXSAVE instruction, see the  [Intel 64 and IA-32 Architectures Software Developer's Manual](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html). |
|  XPF_CONTEXT_INFO_32BITDEBUGREGS | 32-bit debug registers. The buffer contains an array of eight 64-bit values that contain the 32-bit debug registers DR0-DR7. Each of the 32-bit debug registers are zero-extended to 64-bits.  |
| XPF_CONTEXT_INFO_64BITDEBUGREGS  | 64-bit debug registers. The buffer contains an array of eight 64-bit values that contain the 64-bit debug registers DR0-DR7.  |
| XPF_CONTEXT_INFO_MMREGISTERS  | The buffer contains an array of 64-bit memory mapped registers. The number of registers in the array is determined by dividing the size specified in the RegisterDataSize member by eight.  |

### -field RegisterDataSize

The size, in bytes, of the register data that is contained in the **RegisterData** member.

### -field MSRAddress

The starting address of the machine-specific registers. This member contains valid data only if the **RegisterContextType** member is set to either XPF_CONTEXT_INFO_UNCLASSIFIEDDATA or XPF_CONTEXT_INFO_MSRREGISTERS. For all other types of processor context information, this member should contain zero.

### -field MmRegisterAddress

The starting memory address of the memory mapped registers. This member contains valid data only if the **RegisterContextType** member is set to XPF_CONTEXT_INFO_MMREGISTERS. For all other types of processor context information, this member should contain zero.

## -remarks

The **VariableInfo** member of the [**WHEA_XPF_PROCESSOR_ERROR_SECTION**](/previous-versions/ff560655(v=vs.85)) structure contains zero or more WHEA_XPF_CONTEXT_INFO structures, each of which describes specific context information associated with the processor error that occurred. If the size of a particular WHEA_XPF_CONTEXT_INFO structure is not an even multiple of 16 bytes, the space that is allocated for the structure in the buffer will be padded with additional bytes that are set to zero to round the allocated space up to an even multiple of 16 bytes.

## -see-also

[**WHEA_X64_REGISTER_STATE**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_x64_register_state)

[**WHEA_X86_REGISTER_STATE**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_x86_register_state)

[**WHEA_XPF_PROCESSOR_ERROR_SECTION**](/previous-versions/ff560655(v=vs.85))
