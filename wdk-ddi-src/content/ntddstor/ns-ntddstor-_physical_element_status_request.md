---
UID: NS:ntddstor._PHYSICAL_ELEMENT_STATUS_REQUEST
title: _PHYSICAL_ELEMENT_STATUS_REQUEST (ntddstor.h)
description: The PHYSICAL_ELEMENT_STATUS_REQUEST structure defines the starting element to look for the physical element status of a device.
tech.root: storage
ms.assetid: 982f2bcd-3206-458c-af5d-9a01dddb1a8c
ms.date: 09/10/2018
keywords: ["PHYSICAL_ELEMENT_STATUS_REQUEST structure"]
ms.keywords: _PHYSICAL_ELEMENT_STATUS_REQUEST, PHYSICAL_ELEMENT_STATUS_REQUEST, *PPHYSICAL_ELEMENT_STATUS_REQUEST,
req.header: ntddstor.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: PHYSICAL_ELEMENT_STATUS_REQUEST, *PPHYSICAL_ELEMENT_STATUS_REQUEST
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _PHYSICAL_ELEMENT_STATUS_REQUEST
 - ntddstor/_PHYSICAL_ELEMENT_STATUS_REQUEST
 - PPHYSICAL_ELEMENT_STATUS_REQUEST
 - ntddstor/PPHYSICAL_ELEMENT_STATUS_REQUEST
 - PHYSICAL_ELEMENT_STATUS_REQUEST
 - ntddstor/PHYSICAL_ELEMENT_STATUS_REQUEST
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _PHYSICAL_ELEMENT_STATUS_REQUEST
dev_langs:
 - c++
---

# _PHYSICAL_ELEMENT_STATUS_REQUEST structure


## -description

The **PHYSICAL_ELEMENT_STATUS_REQUEST** structure defines the starting element to look for the physical element status of a device.

## -struct-fields

### -field Version

Specifies the version of this structure.

### -field Size

Specifies the size of this structure, in bytes.

### -field StartingElement

Specifies the element identifier of the first physical element addressed by this command.

### -field Filter

Restricts the physical element status descriptors to return based on the following values:

| Value | Meaning |
| --- | --- |
| 0 | All physical status descriptors are specified by the other fields in the CDB. |
| 1 | Only physical element status descriptors for which the value of **PhysicalElementHealth** in [**PHYSICAL_ELEMENT_STATUS_DESCRIPTOR**](ns-ntddstor-_physical_element_status_descriptor.md) is either: <ul><li>Greater than or equal to 0x65 and less than or equal to 0xCF.</li><li>Equal to 0xFF.</li></ul> |

### -field ReportType

 
Specifies the type of physical element status descriptors to return as defined in the following table:

| Value | Meaning |
| --- | --- |
| 0x0 | Return descriptors for physical elements, based on the value of **Filter**. |
| 0x1 | Return descriptors for storage elements, based on the value of **Filter**. |

### -field Reserved

 
Reserved for future use.

## -remarks

This structure is an input buffer for [**IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS**](ni-ntddstor-ioctl_storage_get_physical_element_status.md).

## -see-also

[**IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS**](ni-ntddstor-ioctl_storage_get_physical_element_status.md)

[**PHYSICAL_ELEMENT_STATUS_DESCRIPTOR**](ns-ntddstor-_physical_element_status_descriptor.md)

