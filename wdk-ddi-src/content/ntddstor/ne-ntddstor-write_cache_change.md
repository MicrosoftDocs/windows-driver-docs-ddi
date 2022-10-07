---
UID: NE:ntddstor._WRITE_CACHE_CHANGE
tech.root: storage
title: WRITE_CACHE_CHANGE
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the WRITE_CACHE_CHANGE enumeration.
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
 - _WRITE_CACHE_CHANGE
 - WRITE_CACHE_CHANGE
f1_keywords:
 - _WRITE_CACHE_CHANGE
 - ntddstor/_WRITE_CACHE_CHANGE
 - WRITE_CACHE_CHANGE
 - ntddstor/WRITE_CACHE_CHANGE
dev_langs:
 - c++
helpviewer_keywords:
 - _WRITE_CACHE_CHANGE
---

## -description

The WRITE\_CACHE\_CHANGE enumeration indicates whether the write cache features of a device are changeable or not.

## -enum-fields

### -field WriteCacheChangeUnknown

The system cannot report the write cache change capability of the device.

### -field WriteCacheNotChangeable

Host software cannot change the characteristics of the device's write cache.

### -field WriteCacheChangeable

Host software can change the characteristics of the device's write cache.

## -remarks

The [**IOCTL\_STORAGE\_QUERY\_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request reports a WRITE\_CACHE\_CHANGE value in the [**STORAGE\_WRITE\_CACHE\_PROPERTY**](ns-ntddstor-_storage_write_cache_property.md) structure.

## -see-also

[**IOCTL\_STORAGE\_QUERY\_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE\_WRITE\_CACHE\_PROPERTY**](ns-ntddstor-_storage_write_cache_property.md)
