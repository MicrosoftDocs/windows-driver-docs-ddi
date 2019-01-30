---
UID: NS:ntddstor._PHYSICAL_ELEMENT_STATUS
title: _PHYSICAL_ELEMENT_STATUS (ntddstor.h)
description: The PHYSICAL_ELEMENT_STATUS structure defines the output buffer for IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS.
ms.assetid: 11c8f210-a836-4c73-a69a-160ff113894c
ms.date: 09/10/2018
ms.topic: struct
ms.keywords: _PHYSICAL_ELEMENT_STATUS, PHYSICAL_ELEMENT_STATUS, *PPHYSICAL_ELEMENT_STATUS, 
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
req.typenames: PHYSICAL_ELEMENT_STATUS, *PPHYSICAL_ELEMENT_STATUS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntddstor.h
api_name: 
-	_PHYSICAL_ELEMENT_STATUS
product: Windows
targetos: Windows
ms.custom: RS5
---

# _PHYSICAL_ELEMENT_STATUS structure

## -description

The **PHYSICAL_ELEMENT_STATUS** structure defines the output buffer for [**IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS**](ni-ntddstor-ioctl_storage_get_physical_element_status.md).

## -struct-fields

### -field Version

Specifies the version of this structure.
 
### -field Size

Specifies the size of this structure, in bytes.
 
### -field DescriptorCount

Specifies the number of descriptors in the element descriptors list given as input in [**PHYSICAL_ELEMENT_STATUS_REQUEST**](ns-ntddstor-_physical_element_status_request.md).
 
### -field ReturnedDescriptorCount

Specifies the number of valid descriptors returned.
 
### -field ElementIdentifierBeingDepoped

Specifies the element identifier of a de-popped descriptor.
 
### -field Reserved

Reserved for future use.
 
### -field Descriptors

The valid descriptors sorted in ascending order based on the element identifier. 

## -remarks

## -see-also

[**IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS**](ni-ntddstor-ioctl_storage_get_physical_element_status.md)

[**PHYSICAL_ELEMENT_STATUS_REQUEST**](ns-ntddstor-_physical_element_status_request.md)

[**PHYSICAL_ELEMENT_STATUS_DESCRIPTOR**](ns-ntddstor-_physical_element_status_descriptor.md)
