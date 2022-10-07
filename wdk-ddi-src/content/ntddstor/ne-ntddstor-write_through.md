---
UID: NE:ntddstor._WRITE_THROUGH
tech.root: storage
title: WRITE_THROUGH
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the WRITE_THROUGH enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _WRITE_THROUGH
 - WRITE_THROUGH
f1_keywords:
 - _WRITE_THROUGH
 - ntddstor/_WRITE_THROUGH
 - WRITE_THROUGH
 - ntddstor/WRITE_THROUGH
dev_langs:
 - c++
helpviewer_keywords:
 - _WRITE_THROUGH
---

## -description

The WRITE\_THROUGH enumeration specifies whether a storage device supports write-through caching.

## -enum-fields

### -field WriteThroughUnknown

Indicates that no information is available concerning the writethrough capabilities of the device.

### -field WriteThroughNotSupported

Indicates that the device does not support writethrough operations.

### -field WriteThroughSupported

Indicates that the device supports writethrough operations.

## -remarks

The [**IOCTL\_STORAGE\_QUERY\_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request reports this value in the [**STORAGE\_WRITE\_CACHE\_PROPERTY**](ns-ntddstor-_storage_write_cache_property.md) structure.

## -see-also

[**IOCTL\_STORAGE\_QUERY\_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE\_WRITE\_CACHE\_PROPERTY**](ns-ntddstor-_storage_write_cache_property.md)
