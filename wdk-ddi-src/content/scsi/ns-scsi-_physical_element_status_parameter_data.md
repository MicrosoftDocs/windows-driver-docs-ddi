---
UID: NS:scsi._PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA
title: _PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA (scsi.h)
description: The PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA structure contains the parameter data for a physical element.
ms.assetid: abd6528d-d343-4239-aa83-4b217945b233
ms.date: 09/10/2018
keywords: ["PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA structure"]
ms.keywords: _PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA, PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA, *PPHYSICAL_ELEMENT_STATUS_PARAMETER_DATA,
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
req.typenames: PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA, *PPHYSICAL_ELEMENT_STATUS_PARAMETER_DATA
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA
 - scsi/_PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA
 - PPHYSICAL_ELEMENT_STATUS_PARAMETER_DATA
 - scsi/PPHYSICAL_ELEMENT_STATUS_PARAMETER_DATA
 - PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA
 - scsi/PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - _PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA
dev_langs:
 - c++
---

# _PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA structure


## -description

The **PHYSICAL_ELEMENT_STATUS_PARAMETER_DATA** structure contains the parameter data for a physical element.

## -struct-fields

### -field DescriptorCount

Specifies the number of descriptors in the element descriptors list given as input in [**PHYSICAL_ELEMENT_STATUS_REQUEST**](../ntddstor/ns-ntddstor-_physical_element_status_request.md).

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

[**PHYSICAL_ELEMENT_STATUS_REQUEST**](../ntddstor/ns-ntddstor-_physical_element_status_request.md)

[**PHYSICAL_ELEMENT_STATUS_DATA_DESCRIPTOR**](ns-scsi-_physical_element_status_data_descriptor.md)

