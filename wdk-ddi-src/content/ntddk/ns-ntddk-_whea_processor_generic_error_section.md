---
UID: NS:ntddk._WHEA_PROCESSOR_GENERIC_ERROR_SECTION
title: _WHEA_PROCESSOR_GENERIC_ERROR_SECTION (ntddk.h)
description: Describes processor error data that is not specific to a particular processor architecture.
tech.root: whea
ms.date: 03/13/2023
keywords: ["WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure"]
ms.keywords: "*PWHEA_GENERIC_PROCESSOR_ERROR, *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION, GENPROC_FLAGS_CORRECTED, GENPROC_FLAGS_OVERFLOW, GENPROC_FLAGS_PRECISEIP, GENPROC_FLAGS_RESTARTABLE, GENPROC_OP_DATAREAD, GENPROC_OP_DATAWRITE, GENPROC_OP_GENERIC, GENPROC_OP_INSTRUCTIONEXE, GENPROC_PROCERRTYPE_BUS, GENPROC_PROCERRTYPE_CACHE, GENPROC_PROCERRTYPE_MAE, GENPROC_PROCERRTYPE_TLB, GENPROC_PROCERRTYPE_UNKNOWN, GENPROC_PROCISA_IPF, GENPROC_PROCISA_X64, GENPROC_PROCISA_X86, GENPROC_PROCTYPE_IPF, GENPROC_PROCTYPE_XPF, PWHEA_PROCESSOR_GENERIC_ERROR_SECTION, PWHEA_PROCESSOR_GENERIC_ERROR_SECTION structure pointer [WHEA Drivers and Applications], WHEA_GENERIC_PROCESSOR_ERROR, WHEA_PROCESSOR_GENERIC_ERROR_SECTION, WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure [WHEA Drivers and Applications], _WHEA_PROCESSOR_GENERIC_ERROR_SECTION, ntddk/PWHEA_PROCESSOR_GENERIC_ERROR_SECTION, ntddk/WHEA_PROCESSOR_GENERIC_ERROR_SECTION, whea.whea_processor_generic_error_section, whearef_589ac6c8-3889-4033-8776-0d8f402d1f69.xml"
req.header: ntddk.h
req.include-header: 
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
req.typenames: WHEA_PROCESSOR_GENERIC_ERROR_SECTION, *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION
f1_keywords:
 - _WHEA_PROCESSOR_GENERIC_ERROR_SECTION
 - ntddk/_WHEA_PROCESSOR_GENERIC_ERROR_SECTION
 - PWHEA_PROCESSOR_GENERIC_ERROR_SECTION
 - ntddk/PWHEA_PROCESSOR_GENERIC_ERROR_SECTION
 - WHEA_PROCESSOR_GENERIC_ERROR_SECTION
 - ntddk/WHEA_PROCESSOR_GENERIC_ERROR_SECTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_PROCESSOR_GENERIC_ERROR_SECTION
 - PWHEA_PROCESSOR_GENERIC_ERROR_SECTION
 - WHEA_PROCESSOR_GENERIC_ERROR_SECTION
---

## -description

The **WHEA_PROCESSOR_GENERIC_ERROR_SECTION** structure describes processor error data that is not specific to a particular processor architecture.

## -struct-fields

### -field ValidBits

A [**WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS**](./ns-ntddk-_whea_processor_generic_error_section_validbits.md) union that specifies which members of this structure contain valid data.

### -field ProcessorType

The processor architecture of the processor.

This member contains valid data only if the **ProcessorType** bit of the **ValidBits** member is set.

| Value | Description |
|---|---|
| GENPROC_PROCTYPE_XPF | x86/x64 processor family |
| GENPROC_PROCTYPE_IPF | Intel Itanium processor family |

### -field InstructionSet

The instruction set that was executing when the error occurred.

This member contains valid data only if the **InstructionSet** bit of the **ValidBits** member is set.

| Value | Description |
|---|---|
| GENPROC_PROCISA_X86 | x86 |
| GENPROC_PROCISA_IPF | Itanium |
| GENPROC_PROCISA_X64 | x64 |

### -field ErrorType

The type of error that occurred.

This member contains valid data only if the **ErrorType** bit of the **ValidBits** member is set.

| Value | Description |
|---|---|
| GENPROC_PROCERRTYPE_UNKNOWN | Unknown error |
| GENPROC_PROCERRTYPE_CACHE | Cache error |
| GENPROC_PROCERRTYPE_TLB | Translation lookaside buffer error |
| GENPROC_PROCERRTYPE_BUS | Bus error |
| GENPROC_PROCERRTYPE_MAE | Microarchitecture error |

### -field Operation

The type of operation that was executing when the error occurred.

This member contains valid data only if the **Operation** bit of the **ValidBits** member is set.

| Value | Description |
|---|---|
| GENPROC_OP_GENERIC | Unknown or generic operation |
| GENPROC_OP_DATAREAD | Data read |
| GENPROC_OP_DATAWRITE | Data write |
| GENPROC_OP_INSTRUCTIONEXE | Instruction execution |

### -field Flags

A bit-wise OR'ed combination of flags that provides additional information about the error.

This member contains valid data only if the **Flags** bit of the **ValidBits** member is set.

| Value | Description |
|---|---|
| GENPROC_FLAGS_RESTARTABLE | Program execution can be restarted reliably after the error. |
| GENPROC_FLAGS_PRECISEIP | The instruction pointer in the **InstructionPointer** member is directly associated with the error. |
| GENPROC_FLAGS_OVERFLOW | A machine check overflow occurred. This happens when a second error occurs while the results of the previous error are still in the error reporting resources. |
| GENPROC_FLAGS_CORRECTED | The error was corrected by the hardware or the firmware. |

### -field Level

The level of the structure where the error occurred, with zero being the lowest level of cache.

This member contains valid data only if the **Level** bit of the **ValidBits** member is set.

### -field Reserved

Reserved for system use.

### -field CPUVersion

The CPU version, which includes the family, model, and stepping information.

- For x86 and x64 processors, this member contains a [**WHEA_PROCESSOR_FAMILY_INFO**](./ns-ntddk-_whea_processor_family_info.md) union.

- For Itanium processors, this member contains the data provided in CPUID Register 3.

This member contains valid data only if the **CPUVersion** bit of the **ValidBits** member is set.

### -field CPUBrandString

The CPU brand string.

- For x86 and x64 processors, this member contains the result of executing the CPUID instruction with EAX set to 0x80000002 on input, followed by executing the CPUID instruction with EAX set to 0x80000003 on input. For more information about the CPUID instruction, see the [Intel 64 and IA-32 Architectures Software Developer's Manual](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html)

- For Itanium processors, this member contains the result of executing the **PAL_BRAND_INFO** procedure.

This member contains valid data only if the **CpuBrandString** bit of the **ValidBits** member is set.

### -field ProcessorId

An identifier that uniquely identifies the logical processor in the system.

- For x86 and x64 processors, this member contains the value programmed into the local APIC ID register.

- For Itanium processors, this member contains the value programmed into the LID register.

This member contains valid data only if the **ProcessorId** bit of the **ValidBits** member is set.

### -field TargetAddress

The target address associated with the error.

This member contains valid data only if the **TargetAddress** bit of the **ValidBits** member is set.

### -field RequesterId

An identifier that uniquely identifies the requester associated with the error.

This member contains valid data only if the **RequesterId** bit of the **ValidBits** member is set.

### -field ResponderId

An identifier that uniquely identifies the responder associated with the error.

This member contains valid data only if the **ResponderId** bit of the **ValidBits** member is set.

### -field InstructionPointer

The instruction pointer at the time that the error occurred.

This member contains valid data only if the **InstructionPointer** bit of the **ValidBits** member is set.

## -remarks

The **WHEA_PROCESSOR_GENERIC_ERROR_SECTION** structure describes the error data that is contained in a generic processor error section of an  [error record](/windows-hardware/drivers/whea/error-records). An error record contains a generic processor error section only if the **SectionType** member of one of the [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structures that describe the error record sections for that error record contains **PROCESSOR_GENERIC_ERROR_SECTION_GUID**.

## -see-also

[**WHEA_ERROR_PACKET**](/previous-versions/windows/hardware/drivers/ff560465(v=vs.85))

[**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md)

[**WHEA_PROCESSOR_FAMILY_INFO**](./ns-ntddk-_whea_processor_family_info.md)

[**WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS**](./ns-ntddk-_whea_processor_generic_error_section_validbits.md)