---
UID: NS:ntddstor._PHYSICAL_ELEMENT_STATUS_DESCRIPTOR
title: _PHYSICAL_ELEMENT_STATUS_DESCRIPTOR
author: windows-driver-content
description: The PHYSICAL_ELEMENT_STATUS_DESCRIPTOR structure contains status information for a physical element.
ms.assetid: 60abea0f-4729-413f-909f-295bbf513cd2
ms.date: 09/10/2018
ms.topic: struct
ms.keywords: _PHYSICAL_ELEMENT_STATUS_DESCRIPTOR, PHYSICAL_ELEMENT_STATUS_DESCRIPTOR, *PPHYSICAL_ELEMENT_STATUS_DESCRIPTOR, 
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
req.typenames: PHYSICAL_ELEMENT_STATUS_DESCRIPTOR, *PPHYSICAL_ELEMENT_STATUS_DESCRIPTOR
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntddstor.h
api_name: 
-	_PHYSICAL_ELEMENT_STATUS_DESCRIPTOR
product: Windows
targetos: Windows
ms.custom: RS5
---

# _PHYSICAL_ELEMENT_STATUS_DESCRIPTOR structure

## -description

The **PHYSICAL_ELEMENT_STATUS_DESCRIPTOR** structure contains status information for a physical element.

## -struct-fields

### -field Version

Specifies the version of this structure.
 
### -field Size

Specifies the size of this structure, in bytes.
 
### -field ElementIdentifier

Specifies the identifier of the physical element associated with this Physical Element Status descriptor.
 
### -field PhysicalElementType

Indicates the type of the physical element associated with this Physical Element Status descriptor, as described in the following table.

| Value | Meaning |
| --- | --- |
| 0x01 | Storage Element |
 
### -field PhysicalElementHealth

Indicates the health of the physical element associated with this Physical Element Status descriptor, as described in the following table.

| Value | Meaning |
| --- | --- |
| 0x00 | Not reported. |
| 0x01 to 0x63 | Within manufacturer’s specification limits. |
| 0x64 | At manufacturer’s specification limit. |
| 0x65 to 0xCF | Outside manufacturer’s specification limit. | 
| 0xD0 to 0xFE | Reserved. |
| 0xFF | Depopulated. |
 
### -field Reserved1

Reserved for future use.
 
### -field AssociatedCapacity

Indicates the number of logical blocks by which the capacity of the device is reduced if the physical element associated with this Physical Element Status descriptor becomes depopulated.
 
### -field Reserved2
 
Reserved for future use.

## -remarks

## -see-also

[**PHYSICAL_ELEMENT_STATUS**](ns-ntddstor-_physical_element_status.md)
