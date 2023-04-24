---
UID: NE:ntddstor._WRITE_CACHE_TYPE
tech.root: storage
title: WRITE_CACHE_TYPE
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the WRITE_CACHE_TYPE enumeration.
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
 - _WRITE_CACHE_TYPE
 - WRITE_CACHE_TYPE
f1_keywords:
 - _WRITE_CACHE_TYPE
 - ntddstor/_WRITE_CACHE_TYPE
 - WRITE_CACHE_TYPE
 - ntddstor/WRITE_CACHE_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _WRITE_CACHE_TYPE
---

## -description

The WRITE\_CACHE\_TYPE enumeration specifies the cache type.

## -enum-fields

### -field WriteCacheTypeUnknown

The system cannot report the type of the write cache.

### -field WriteCacheTypeNone

The system cannot report the type of the write cache.

### -field WriteCacheTypeWriteBack

The device has a write back cache.

### -field WriteCacheTypeWriteThrough

The device has a write through cache.

## -remarks

There are two main types of write cache: *write back* and *write through*. With a write-back cache, the device does not copy cache data to nonvolatile media until absolutely necessary. This type of operation improves the performance of write operations. With a write-through cache, the device writes data to the cache and the media in parallel. This type of operation does not improve write performance, but it makes subsequent read operations faster.

The [**IOCTL\_STORAGE\_QUERY\_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request reports a WRITE\_CACHE\_TYPE value in the [**STORAGE\_WRITE\_CACHE\_PROPERTY**](ns-ntddstor-_storage_write_cache_property.md) structure.

## -see-also

[**IOCTL\_STORAGE\_QUERY\_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE\_WRITE\_CACHE\_PROPERTY**](ns-ntddstor-_storage_write_cache_property.md)
