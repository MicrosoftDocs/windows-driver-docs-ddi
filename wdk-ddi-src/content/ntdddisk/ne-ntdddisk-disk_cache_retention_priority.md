---
UID: NE:ntdddisk.DISK_CACHE_RETENTION_PRIORITY
title: DISK_CACHE_RETENTION_PRIORITY (ntdddisk.h)
description: The DISK_CACHE_RETENTION_PRIORITY enumeration is used in conjunction with the IOCTL_DISK_GET_CACHE_INFORMATION request and the structure DISK_CACHE_INFORMATION to indicate which kinds data are to be held in the cache on a preferential basis.
old-location: storage\disk_cache_retention_priority.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["DISK_CACHE_RETENTION_PRIORITY enumeration"]
ms.keywords: DISK_CACHE_RETENTION_PRIORITY, DISK_CACHE_RETENTION_PRIORITY enumeration [Storage Devices], EqualPriority, KeepPrefetchedData, KeepReadData, ntdddisk/DISK_CACHE_RETENTION_PRIORITY, ntdddisk/EqualPriority, ntdddisk/KeepPrefetchedData, ntdddisk/KeepReadData, storage.disk_cache_retention_priority, structs-disk_19939b68-659e-4546-8419-7e1e141b8291.xml
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
req.typenames: DISK_CACHE_RETENTION_PRIORITY
f1_keywords:
 - DISK_CACHE_RETENTION_PRIORITY
 - ntdddisk/DISK_CACHE_RETENTION_PRIORITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - DISK_CACHE_RETENTION_PRIORITY
---

# DISK_CACHE_RETENTION_PRIORITY enumeration


## -description

The DISK_CACHE_RETENTION_PRIORITY enumeration is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_cache_information">IOCTL_DISK_GET_CACHE_INFORMATION</a> request and the structure <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_cache_information">DISK_CACHE_INFORMATION</a> to indicate which kinds data are to be held in the cache on a preferential basis.

## -enum-fields

### -field EqualPriority

Indicates that no data is held in the cache on a preferential basis. All types of data have equal access to cache memory.

### -field KeepPrefetchedData

Indicates that a preference is to be given to prefetched data.

### -field KeepReadData

Indicates that a preference is to be given to data cached from a READ operation.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_cache_information">DISK_CACHE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_cache_information">IOCTL_DISK_GET_CACHE_INFORMATION</a>

