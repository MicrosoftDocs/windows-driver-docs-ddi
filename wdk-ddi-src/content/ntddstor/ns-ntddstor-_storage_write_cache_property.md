---
UID: NS:ntddstor._STORAGE_WRITE_CACHE_PROPERTY
title: _STORAGE_WRITE_CACHE_PROPERTY (ntddstor.h)
description: The STORAGE_WRITE_CACHE_PROPERTY structure is used with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve information about a device's write cache property.
old-location: storage\storage_write_cache_property.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STORAGE_WRITE_CACHE_PROPERTY structure"]
ms.keywords: PSTORAGE_WRITE_CACHE_PROPERTY, PSTORAGE_WRITE_CACHE_PROPERTY structure pointer [Storage Devices], STORAGE_WRITE_CACHE_PROPERTY, STORAGE_WRITE_CACHE_PROPERTY structure [Storage Devices], _STORAGE_WRITE_CACHE_PROPERTY, ntddstor/PSTORAGE_WRITE_CACHE_PROPERTY, ntddstor/STORAGE_WRITE_CACHE_PROPERTY, storage.storage_write_cache_property, structs-general_9c0929be-3c02-4f48-a6be-e24c42b0783c.xml
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: STORAGE_WRITE_CACHE_PROPERTY, PSTORAGE_WRITE_CACHE_PROPERTY
f1_keywords:
 - _STORAGE_WRITE_CACHE_PROPERTY
 - ntddstor/_STORAGE_WRITE_CACHE_PROPERTY
 - PSTORAGE_WRITE_CACHE_PROPERTY
 - ntddstor/PSTORAGE_WRITE_CACHE_PROPERTY
 - STORAGE_WRITE_CACHE_PROPERTY
 - ntddstor/STORAGE_WRITE_CACHE_PROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_WRITE_CACHE_PROPERTY
---

# _STORAGE_WRITE_CACHE_PROPERTY structure


## -description

The STORAGE_WRITE_CACHE_PROPERTY structure is used with the <a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve information about a device's write cache property.

## -struct-fields

### -field Version

The version number of the write cache property.

### -field Size

The size, in bytes, of the STORAGE_WRITE_CACHE_PROPERTY structure.

### -field WriteCacheType

A <a href="/previous-versions/windows/hardware/drivers/ff568044(v=vs.85)">WRITE_CACHE_TYPE</a>-typed value that indicates the current write cache type

### -field WriteCacheEnabled

A <a href="/previous-versions/windows/hardware/drivers/ff568042(v=vs.85)">WRITE_CACHE_ENABLE</a>-typed value that indicates whether the write cache is enabled.

### -field WriteCacheChangeable

A <a href="/previous-versions/windows/hardware/drivers/ff568039(v=vs.85)">WRITE_CACHE_CHANGE</a>-typed value that indicates whether if the host can change the write cache characteristics.

### -field WriteThroughSupported

A <a href="/previous-versions/windows/hardware/drivers/ff568047(v=vs.85)">WRITE_THROUGH</a>-typed value that indicates whether the device supports write-through caching.

### -field FlushCacheSupported

A Boolean value that indicates whether the device allows host software to flush the device cache. If <b>TRUE</b>, the device allows host software to flush the device cache. If <b>FALSE</b>, host software cannot flush the device cache.

### -field UserDefinedPowerProtection

A Boolean value that indicates whether a user can configure the device's power protection characteristics in the registry. If <b>TRUE</b>, a user can configure the device's power protection characteristics in the registry. If <b>FALSE</b>, the user cannot configure the device's power protection characteristics in the registry.

### -field NVCacheEnabled

A Boolean value that indicates whether the device has a battery backup for the write cache. If <b>TRUE</b>, the device has a battery backup for the write cache. If <b>FALSE</b>, the device does not have a battery backup for the writer cache.

## -remarks

All of the parameter values that are described in this topic refer to the output of the <a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>
