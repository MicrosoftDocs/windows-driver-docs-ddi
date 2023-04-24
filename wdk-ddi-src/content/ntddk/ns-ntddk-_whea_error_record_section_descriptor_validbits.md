---
UID: NS:ntddk._WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
title: WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS (ntddk.h)
description: The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union describes which members of a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure contain valid data.
tech.root: whea
ms.date: 12/09/2022
keywords: ["WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS structure"]
ms.keywords: "*PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union [WHEA Drivers and Applications], _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, ntddk/PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, ntddk/WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, whea.whea_error_record_section_descriptor_validbits, whearef_0e13e9d6-57cb-44bd-825e-d9cab5c138c8.xml"
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
req.typenames: WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
f1_keywords:
 - _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
 - ntddk/_WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
 - PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
 - ntddk/PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
 - WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
 - ntddk/WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
 - PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
 - WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
---

## -description

The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union describes which members of a [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure contain valid data.

## -struct-fields

### -field DUMMYSTRUCTNAME

Defines the **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.FRUId

A single bit that indicates that the **FRUId** member of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure contains valid data.

### -field DUMMYSTRUCTNAME.FRUText

A single bit that indicates that the **FRUText** member of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure contains valid data.

### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.

### -field AsUCHAR

A UCHAR representation of the contents of the **WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS** union.

## -remarks

A WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union is contained within the [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure.

## -see-also

[**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md)