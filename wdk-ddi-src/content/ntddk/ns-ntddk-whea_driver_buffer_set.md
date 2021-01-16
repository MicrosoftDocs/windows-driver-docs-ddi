---
UID: NS:ntddk._WHEA_DRIVER_BUFFER_SET
title: WHEA_DRIVER_BUFFER_SET
ms.date: 04/02/2020
tech.root: whea
ms.topic: language-reference
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: WHEA_DRIVER_BUFFER_SET, *PWHEA_DRIVER_BUFFER_SET
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_DRIVER_BUFFER_SET
 - PWHEA_DRIVER_BUFFER_SET
 - WHEA_DRIVER_BUFFER_SET
f1_keywords:
 - _WHEA_DRIVER_BUFFER_SET
 - ntddk/_WHEA_DRIVER_BUFFER_SET
 - PWHEA_DRIVER_BUFFER_SET
 - ntddk/PWHEA_DRIVER_BUFFER_SET
 - WHEA_DRIVER_BUFFER_SET
 - ntddk/WHEA_DRIVER_BUFFER_SET
dev_langs:
 - c++
---

## -description

This structure stores WHEA error report data.

## -struct-fields

### -field Version

Not currently used.

### -field Data

A pointer to a buffer containing data to be added to the body of the section.

### -field DataSize

Length, in bytes, of buffer specified by *Data*. Must be equal to *SectionDataLength* specified in [**WheaAddHwErrorReportSectionDeviceDriver**](nf-ntddk-wheaaddhwerrorreportsectiondevicedriver.md).

### -field SectionTypeGuid

A GUID used in the header of the section for differentiation, and by tools like Dumprec for parsing records.

### -field SectionFriendlyName

Pointer to a string containing a human readable name added to the header information.

### -field Flags

Not currently used.

## -remarks

[**WheaAddHwErrorReportSectionDeviceDriver**](nf-ntddk-wheaaddhwerrorreportsectiondevicedriver.md) takes as a parameter a pointer to a structure of this type. Upon success, it stores data in the structure.

## -see-also

