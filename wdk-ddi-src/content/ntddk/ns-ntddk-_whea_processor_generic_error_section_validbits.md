---
UID: NS:ntddk._WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS
title: _WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS (ntddk.h)
description: The WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contain valid data.
old-location: whea\whea_processor_generic_error_section_validbits.htm
tech.root: whea
ms.assetid: f7173767-a177-4a79-917b-41acc9eff758
ms.date: 02/20/2018
keywords: ["_WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS structure"]
ms.keywords: "*PWHEA_GENERIC_PROCESSOR_ERROR_VALIDBITS, *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_GENERIC_PROCESSOR_ERROR_VALIDBITS, WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], _WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, ntddk/WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, whea.whea_processor_generic_error_section_validbits, whearef_83372975-ce45-44e7-be0a-85f3394528b3.xml"
f1_keywords:
 - "ntddk/WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS
product:
- Windows
targetos: Windows
req.typenames: WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS
---

# _WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS structure


## -description


The WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union describes which members of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure contain valid data.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.ProcessorType

A single bit that indicates that the <b>ProcessorType</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.InstructionSet

A single bit that indicates that the <b>InstructionSet</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ErrorType

A single bit that indicates that the <b>ErrorType</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Operation

A single bit that indicates that the <b>Operation</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Flags

A single bit that indicates that the <b>Flags</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Level

A single bit that indicates that the <b>Level</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.CPUVersion

A single bit that indicates that the <b>CPUVersion</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.CPUBrandString

A single bit that indicates that the <b>CPUBrandString</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ProcessorId

A single bit that indicates that the <b>ProcessorId</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.TargetAddress

A single bit that indicates that the <b>TargetAddress</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.RequesterId

A single bit that indicates that the <b>RequesterId</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ResponderId

A single bit that indicates that the <b>ResponderId</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.InstructionPointer

A single bit that indicates that the <b>InstructionPointer</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union.


## -remarks



A WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union is contained within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>
 

 

