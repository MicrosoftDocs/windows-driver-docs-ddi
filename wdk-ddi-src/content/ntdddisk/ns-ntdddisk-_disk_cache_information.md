---
UID: NS:ntdddisk._DISK_CACHE_INFORMATION
title: "_DISK_CACHE_INFORMATION"
author: windows-driver-content
description: The DISK_CACHE_INFORMATION structure is used with the IOCTL_DISK_GET_CACHE_INFORMATION request to retrieve cache information.
old-location: storage\disk_cache_information.htm
old-project: storage
ms.assetid: 17ea8b6b-d41f-4224-880a-49443756d0de
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDISK_CACHE_INFORMATION, DISK_CACHE_INFORMATION, DISK_CACHE_INFORMATION structure [Storage Devices], PDISK_CACHE_INFORMATION, PDISK_CACHE_INFORMATION structure pointer [Storage Devices], _DISK_CACHE_INFORMATION, ntdddisk/DISK_CACHE_INFORMATION, ntdddisk/PDISK_CACHE_INFORMATION, storage.disk_cache_information, structs-disk_def992c5-6103-4eab-8598-4d52808e6b8c.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdddisk.h
api_name:
-	DISK_CACHE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: DISK_CACHE_INFORMATION, *PDISK_CACHE_INFORMATION
---

# _DISK_CACHE_INFORMATION structure


## -description


The DISK_CACHE_INFORMATION structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559451">IOCTL_DISK_GET_CACHE_INFORMATION</a> request to retrieve cache information.


## -struct-fields




### -field ParametersSavable

Indicates, when set to 1, that the device is capable of saving any parameters in nonvolatile storage.


### -field ReadCacheEnabled

Indicates, when set to 1, that the read cache is enabled.


### -field WriteCacheEnabled

Indicates, when set to 1, that the write cache is enabled.


### -field ReadRetentionPriority

Determines the likelihood of various types of data remaining in the cache. By means of this value, for instance, data cached from a READ or WRITE operation might be given a different priority than data cached under other circumstances, such as prefetch operations. Thus a value of <b>EqualPriority</b> indicates that no data is held in the cache on a preferential basis. When <b>ReadRetentionPriority</b> is set to <b>EqualPriority</b>, all types of data have equal access to cache memory. On the other hand, a value of <b>KeepPrefetchedData</b> indicates that a preference is to be given to prefetched data while a value of <b>KeepReadData</b> indicates that a preference is to be given to data cached from a READ operation. For more information about the values that can be assigned to this member see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552583">DISK_CACHE_RETENTION_PRIORITY</a> enumeration. 


### -field WriteRetentionPriority

See discussion under <b>ReadRetentionPriority</b>.


### -field DisablePrefetchTransferLength

Disables prefetching. Prefetching might be disabled whenever the number of blocks requested exceeds the value in <b>DisablePrefetchTransferLength</b>. When zero, prefetching is disabled no matter what the size of the block request.


### -field PrefetchScalar

When <b>TRUE</b>, Indicates that <b>ScalarPrefetch.Maximum</b> should be used together with the transfer length to calculate the amount of data that can be prefetched. When <b>FALSE</b>, <b>BlockPrefetch.Maximum</b> will be the maximum number of disk blocks that can be prefetched.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.ScalarPrefetch


### -field DUMMYUNIONNAME.ScalarPrefetch.Minimum

Contains the scalar multiplier of the transfer length of the request when <b>PrefetchScalar</b> is <b>TRUE</b>. If <b>PrefetchScalar</b> is <b>TRUE</b>, the value in <b>ScalarPrefetch.Minimum</b> is multiplied by the transfer length to obtain the minimum amount of data that can be prefetched into the cache on a disk operation. 


### -field DUMMYUNIONNAME.ScalarPrefetch.Maximum

Contains the scalar multiplier of the transfer length of the request when <b>PrefetchScalar</b> is <b>TRUE</b>. If <b>PrefetchScalar</b> is <b>TRUE</b>, the value in <b>ScalarPrefetch.Maximum</b> is multiplied by the transfer length to obtain the maximum amount of data that can be prefetched into the cache on a disk operation. 


### -field DUMMYUNIONNAME.ScalarPrefetch.MaximumBlocks

Contains the maximum size, in blocks, of the transfer length. 


### -field DUMMYUNIONNAME.BlockPrefetch


### -field DUMMYUNIONNAME.BlockPrefetch.Minimum

Contains the scalar multiplier of the transfer length of the request when <b>PrefetchScalar</b> is <b>TRUE</b>. If <b>PrefetchScalar</b> is <b>TRUE</b>, the value in <b>ScalarPrefetch.Minimum</b> is multiplied by the transfer length to obtain the minimum amount of data that can be prefetched into the cache on a disk operation. 


### -field DUMMYUNIONNAME.BlockPrefetch.Maximum

Contains the scalar multiplier of the transfer length of the request when <b>PrefetchScalar</b> is <b>TRUE</b>. If <b>PrefetchScalar</b> is <b>TRUE</b>, the value in <b>ScalarPrefetch.Maximum</b> is multiplied by the transfer length to obtain the maximum amount of data that can be prefetched into the cache on a disk operation. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552580">DISK_CACHE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559451">IOCTL_DISK_GET_CACHE_INFORMATION</a>
 

 

