---
UID: NS:ntdddisk._DISK_GROW_PARTITION
title: "_DISK_GROW_PARTITION"
author: windows-driver-content
description: The DISK_GROW_PARTITION structure is used in conjunction with the IOCTL_DISK_GROW_PARTITION request to enlarge a partition.
old-location: storage\disk_grow_partition.htm
old-project: storage
ms.assetid: cab9877c-3b7b-4644-83eb-0aa1e9fc77b9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PDISK_GROW_PARTITION, ,, A, D, DISK_GROW_PARTITION, DISK_GROW_PARTITION structure [Storage Devices], G, I, K, N, O, P, PDISK_GROW_PARTITION, PDISK_GROW_PARTITION structure pointer [Storage Devices], R, S, T, W, _, _DISK_GROW_PARTITION, ntdddisk/DISK_GROW_PARTITION, ntdddisk/PDISK_GROW_PARTITION, storage.disk_grow_partition, structs-disk_cc7d52cd-b0b6-4e5c-a323-6d513f37e602.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntdddisk.h
apiname:
-	DISK_GROW_PARTITION
product: Windows
targetos: Windows
req.typenames: DISK_GROW_PARTITION, *PDISK_GROW_PARTITION
---

# _DISK_GROW_PARTITION structure


## -description


The DISK_GROW_PARTITION structure is used in conjunction with the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_grow_partition.md">IOCTL_DISK_GROW_PARTITION</a> request to enlarge a partition. 


## -syntax


````
typedef struct _DISK_GROW_PARTITION {
  ULONG         PartitionNumber;
  LARGE_INTEGER BytesToGrow;
} DISK_GROW_PARTITION, *PDISK_GROW_PARTITION;
````


## -struct-fields




### -field PartitionNumber

Specifies a number identifying the partition to be enlarged.


### -field BytesToGrow

Indicates the number of bytes that the partition should be extended by. Note that this value is not the new size of the partition.


## -see-also

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_grow_partition.md">IOCTL_DISK_GROW_PARTITION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_GROW_PARTITION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

