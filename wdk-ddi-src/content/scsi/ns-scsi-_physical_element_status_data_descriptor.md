---
UID: NS:scsi._PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR
title: _PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR (scsi.h)
description: The PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR structure contains status information for a physical element.
ms.assetid: 55db36a7-f2ad-4246-a1d8-b2a589ee3c61
ms.date: 09/10/2018
keywords: ["_PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR structure"]
f1_keywords:
 - "scsi/_PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR"
 - "_PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR"
ms.keywords: _PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR, PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR, *PPHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR, 
req.header: scsi.h
req.include-header: scsi.h, storport.h, minitape.h
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
req.typenames: PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR, *PPHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- scsi.h
api_name: 
- _PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: RS5
---

# _PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR structure

## -description

The **PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR** structure contains status information for a physical element.

## -struct-fields

### -field Reserved1

Reserved for future use.
 
### -field ElementIdentifier

Indicates the identifier of the physical element associated with this Physical Element Status descriptor.
 
### -field Reserved2

Reserved for future use.
 
### -field PhysicalElementType

Indicates the type of the physical element associated with this Physical Element Status descriptor, as described in the following table.

| Value | Meaning |
| --- | --- |
| **PHYSICAL_ELEMENT_TYPE_STORAGE_ELEMENT** 0x01 | Storage Element |
 
### -field PhysicalElementHealth

Indicates the health of the physical element associated with this Physical Element Status descriptor, as described in the following table.

| Value | Meaning |
| --- | --- |
| 0x00 | Not reported. |
| 0x01 to 0x63 | Within manufacturer’s specification limits. |
| 0x64 | At manufacturer’s specification limit. |
| 0x65 to 0xCF | Outside manufacturer’s specification limit. | 
| 0xD0 to 0xFE | Reserved. |
| 0xFF | Successfully depopulated. |
 
### -field AssociatedCapacity

Indicates the number of logical blocks by which the capacity of the device is reduced if the physical element associated with this Physical Element Status descriptor becomes depopulated.
 
### -field Reserved3

Reserved for future use. 

## -remarks

## -see-also

[**PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA**](ns-scsi-_physical_element_status_parameter_data.md)
