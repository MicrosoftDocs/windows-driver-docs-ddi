---
UID: NE:ntddstor._WRITE_CACHE_ENABLE
tech.root: storage
title: WRITE_CACHE_ENABLE
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the WRITE_CACHE_ENABLE enumeration.
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
 - _WRITE_CACHE_ENABLE
 - WRITE_CACHE_ENABLE
f1_keywords:
 - _WRITE_CACHE_ENABLE
 - ntddstor/_WRITE_CACHE_ENABLE
 - WRITE_CACHE_ENABLE
 - ntddstor/WRITE_CACHE_ENABLE
dev_langs:
 - c++
helpviewer_keywords:
 - _WRITE_CACHE_ENABLE
---

## -description

The WRITE\_CACHE\_ENABLE enumeration indicates whether the write cache is enabled or disabled.

## -enum-fields

### -field WriteCacheEnableUnknown

The system cannot report whether the device's write cache is enabled or disabled.

### -field WriteCacheDisabled

The device's write cache is disabled.

### -field WriteCacheEnabled

The device's write cache is enabled.

## -remarks

The [**IOCTL\_STORAGE\_QUERY\_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request reports a WRITE\_CACHE\_ENABLE value in the [**STORAGE\_WRITE\_CACHE\_PROPERTY**](ns-ntddstor-_storage_write_cache_property.md) structure.

## -see-also

[**IOCTL\_STORAGE\_QUERY\_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE\_WRITE\_CACHE\_PROPERTY**](ns-ntddstor-_storage_write_cache_property.md)
