---
UID: NS:ntddstor._STORAGE_WRITE_CACHE_PROPERTY
title: "_STORAGE_WRITE_CACHE_PROPERTY"
author: windows-driver-content
description: The STORAGE_WRITE_CACHE_PROPERTY structure is used with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve information about a device's write cache property.
old-location: storage\storage_write_cache_property.htm
old-project: storage
ms.assetid: 4abc44ab-1729-46c3-befd-5f917e10953c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PSTORAGE_WRITE_CACHE_PROPERTY, PSTORAGE_WRITE_CACHE_PROPERTY structure pointer [Storage Devices], STORAGE_WRITE_CACHE_PROPERTY, STORAGE_WRITE_CACHE_PROPERTY structure [Storage Devices], _STORAGE_WRITE_CACHE_PROPERTY, ntddstor/PSTORAGE_WRITE_CACHE_PROPERTY, ntddstor/STORAGE_WRITE_CACHE_PROPERTY, storage.storage_write_cache_property, structs-general_9c0929be-3c02-4f48-a6be-e24c42b0783c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_WRITE_CACHE_PROPERTY
product: Windows
targetos: Windows
req.typenames: STORAGE_WRITE_CACHE_PROPERTY, PSTORAGE_WRITE_CACHE_PROPERTY
---

# _STORAGE_WRITE_CACHE_PROPERTY structure


## -description


The STORAGE_WRITE_CACHE_PROPERTY structure is used with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve information about a device's write cache property.


## -syntax


````
typedef struct _STORAGE_WRITE_CACHE_PROPERTY {
  ULONG              Version;
  ULONG              Size;
  WRITE_CACHE_TYPE   WriteCacheType;
  WRITE_CACHE_ENABLE WriteCacheEnabled;
  WRITE_CACHE_CHANGE WriteCacheChangeable;
  WRITE_THROUGH      WriteThroughSupported;
  BOOLEAN            FlushCacheSupported;
  BOOLEAN            UserDefinedPowerProtection;
  BOOLEAN            NVCacheEnabled;
} STORAGE_WRITE_CACHE_PROPERTY, *PSTORAGE_WRITE_CACHE_PROPERTY;
````


## -struct-fields




### -field Version

The version number of the write cache property.


### -field Size

The size, in bytes, of the STORAGE_WRITE_CACHE_PROPERTY structure.


### -field WriteCacheType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff568044">WRITE_CACHE_TYPE</a>-typed value that indicates the current write cache type


### -field WriteCacheEnabled

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff568042">WRITE_CACHE_ENABLE</a>-typed value that indicates whether the write cache is enabled.


### -field WriteCacheChangeable

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff568039">WRITE_CACHE_CHANGE</a>-typed value that indicates whether if the host can change the write cache characteristics.


### -field WriteThroughSupported

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff568047">WRITE_THROUGH</a>-typed value that indicates whether the device supports write-through caching.


### -field FlushCacheSupported

A Boolean value that indicates whether the device allows host software to flush the device cache. If <b>TRUE</b>, the device allows host software to flush the device cache. If <b>FALSE</b>, host software cannot flush the device cache.


### -field UserDefinedPowerProtection

A Boolean value that indicates whether a user can configure the device's power protection characteristics in the registry. If <b>TRUE</b>, a user can configure the device's power protection characteristics in the registry. If <b>FALSE</b>, the user cannot configure the device's power protection characteristics in the registry.


### -field NVCacheEnabled

A Boolean value that indicates whether the device has a battery backup for the write cache. If <b>TRUE</b>, the device has a battery backup for the write cache. If <b>FALSE</b>, the device does not have a battery backup for the writer cache.


## -remarks



All of the parameter values that are described in this topic refer to the output of the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request.




## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_WRITE_CACHE_PROPERTY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

