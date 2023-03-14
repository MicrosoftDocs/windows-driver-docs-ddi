---
UID: NS:ntddk._WHEA_PROCESSOR_FAMILY_INFO
title: _WHEA_PROCESSOR_FAMILY_INFO (ntddk.h)
description: The WHEA_PROCESSOR_FAMILY_INFO union describes the processor family information for an x86 or x64 processor.
old-location: whea\whea_processor_family_info.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["WHEA_PROCESSOR_FAMILY_INFO structure"]
ms.keywords: "*PWHEA_PROCESSOR_FAMILY_INFO, PWHEA_PROCESSOR_FAMILY_INFO, PWHEA_PROCESSOR_FAMILY_INFO union pointer [WHEA Drivers and Applications], WHEA_PROCESSOR_FAMILY_INFO, WHEA_PROCESSOR_FAMILY_INFO union [WHEA Drivers and Applications], _WHEA_PROCESSOR_FAMILY_INFO, ntddk/PWHEA_PROCESSOR_FAMILY_INFO, ntddk/WHEA_PROCESSOR_FAMILY_INFO, whea.whea_processor_family_info, whearef_f15c7bb5-aee5-4a59-9869-285828d92b5e.xml"
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
req.typenames: WHEA_PROCESSOR_FAMILY_INFO, *PWHEA_PROCESSOR_FAMILY_INFO
f1_keywords:
 - _WHEA_PROCESSOR_FAMILY_INFO
 - ntddk/_WHEA_PROCESSOR_FAMILY_INFO
 - PWHEA_PROCESSOR_FAMILY_INFO
 - ntddk/PWHEA_PROCESSOR_FAMILY_INFO
 - WHEA_PROCESSOR_FAMILY_INFO
 - ntddk/WHEA_PROCESSOR_FAMILY_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_PROCESSOR_FAMILY_INFO
 - PWHEA_PROCESSOR_FAMILY_INFO
 - WHEA_PROCESSOR_FAMILY_INFO
---

## -description

The WHEA_PROCESSOR_FAMILY_INFO union describes the processor family information for an x86 or x64 processor.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.Stepping

The stepping of the processor.

### -field DUMMYSTRUCTNAME.Model

The processor model identifier.

### -field DUMMYSTRUCTNAME.Family

The processor family identifier.

### -field DUMMYSTRUCTNAME.ProcessorType

The processor type identifier.

### -field DUMMYSTRUCTNAME.Reserved1

Reserved for system use.

### -field DUMMYSTRUCTNAME.ExtendedModel

The extended processor model identifier.

### -field DUMMYSTRUCTNAME.ExtendedFamily

The extended processor family identifier.

### -field DUMMYSTRUCTNAME.Reserved2

Reserved for system use.

### -field DUMMYSTRUCTNAME.NativeModelId

### -field AsULONGLONG

A ULONGLONG representation of the contents of the WHEA_PROCESSOR_FAMILY_INFO union.

## -remarks

For x86 and x64 processors, the **CPUVersion** member of the [**WHEA_PROCESSOR_GENERIC_ERROR_SECTION**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section) structure contains a WHEA_PROCESSOR_FAMILY_INFO union.

The contents of this union are obtained by executing the CPUID instruction with the EAX register set to 1 on input. For more information about the CPUID instruction, see the [Intel 64 and IA-32 Architectures Software Developer's Manual](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html). For additional information about the data that is contained in the members of this union, see [AP-485 Intel Processor Identification and the CPUID Instruction](https://www.intel.com/content/www/us/en/developer/overview.html).

## -see-also

[WHEA_PROCESSOR_GENERIC_ERROR_SECTION](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section)
