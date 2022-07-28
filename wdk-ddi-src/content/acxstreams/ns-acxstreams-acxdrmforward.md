---
UID: NS:acxstreams._ACXDRMFORWARD
tech.root: audio
title: ACXDRMFORWARD
ms.date: 07/28/2022
targetos: Windows
description: The ACXDRMFORWARD structure contains the information that the DRM system driver needs in order to forward a DRM content ID to a device that handles protected content.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACXDRMFORWARD, *PACXDRMFORWARD
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - _ACXDRMFORWARD
 - PACXDRMFORWARD
 - ACXDRMFORWARD
f1_keywords:
 - _ACXDRMFORWARD
 - acxstreams/_ACXDRMFORWARD
 - PACXDRMFORWARD
 - acxstreams/PACXDRMFORWARD
 - ACXDRMFORWARD
 - acxstreams/ACXDRMFORWARD
dev_langs:
 - c++
---

## -description

The **ACXDRMFORWARD** structure contains the information that the DRM system driver needs in order to forward a DRM content ID to a device that handles protected content.

## -struct-fields

### -field Flags

No flag bits are currently defined. Set this member to zero.

### -field DeviceObject

Pointer to the device object, which is a system structure of type DEVICE_OBJECT.

### -field FileObject

Pointer to the file object, which is a system structure of type FILE_OBJECT.

### -field Context

Pointer to context data.

## -remarks

## -see-also

- [acxstreams.h header](index.md)
