---
UID: NS:ntddk._WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS
title: "_WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS"
author: windows-driver-content
description: The WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contain valid data.
old-location: whea\whea_processor_generic_error_section_validbits.htm
old-project: whea
ms.assetid: f7173767-a177-4a79-917b-41acc9eff758
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_GENERIC_PROCESSOR_ERROR_VALIDBITS, *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_GENERIC_PROCESSOR_ERROR_VALIDBITS, WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], _WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, ntddk/WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, whea.whea_processor_generic_error_section_validbits, whearef_83372975-ce45-44e7-be0a-85f3394528b3.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS
product: Windows
targetos: Windows
req.typenames: WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS
---

# _WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS structure


## -description


The WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union describes which members of a <a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure contain valid data.


## -syntax


````
typedef union _WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS {
  struct {
    ULONGLONG ProcessorType  :1;
    ULONGLONG InstructionSet  :1;
    ULONGLONG ErrorType  :1;
    ULONGLONG Operation  :1;
    ULONGLONG Flags  :1;
    ULONGLONG Level  :1;
    ULONGLONG CPUVersion  :1;
    ULONGLONG CPUBrandString  :1;
    ULONGLONG ProcessorId  :1;
    ULONGLONG TargetAddress  :1;
    ULONGLONG RequesterId  :1;
    ULONGLONG ResponderId  :1;
    ULONGLONG InstructionPointer  :1;
    ULONGLONG Reserved  :51;
  };
  ULONGLONG ValidBits;
} WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union.


#### - ProcessorType

A single bit that indicates that the <b>ProcessorType</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - InstructionSet

A single bit that indicates that the <b>InstructionSet</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - ErrorType

A single bit that indicates that the <b>ErrorType</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - Operation

A single bit that indicates that the <b>Operation</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - Flags

A single bit that indicates that the <b>Flags</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - Level

A single bit that indicates that the <b>Level</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - CPUVersion

A single bit that indicates that the <b>CPUVersion</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - CPUBrandString

A single bit that indicates that the <b>CPUBrandString</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - ProcessorId

A single bit that indicates that the <b>ProcessorId</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - TargetAddress

A single bit that indicates that the <b>TargetAddress</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - RequesterId

A single bit that indicates that the <b>RequesterId</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - ResponderId

A single bit that indicates that the <b>ResponderId</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - InstructionPointer

A single bit that indicates that the <b>InstructionPointer</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.


#### - Reserved

Reserved for system use.


## -remarks



A WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union is contained within the <a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

