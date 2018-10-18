---
UID: NS:ntdddisk._DISK_GROW_PARTITION
title: "_DISK_GROW_PARTITION"
author: windows-driver-content
description: The DISK_GROW_PARTITION structure is used in conjunction with the IOCTL_DISK_GROW_PARTITION request to enlarge a partition.
old-location: storage\disk_grow_partition.htm
tech.root: storage
ms.assetid: cab9877c-3b7b-4644-83eb-0aa1e9fc77b9
ms.date: 3/29/2018
ms.keywords: "*PDISK_GROW_PARTITION, DISK_GROW_PARTITION, DISK_GROW_PARTITION structure [Storage Devices], PDISK_GROW_PARTITION, PDISK_GROW_PARTITION structure pointer [Storage Devices], _DISK_GROW_PARTITION, ntdddisk/DISK_GROW_PARTITION, ntdddisk/PDISK_GROW_PARTITION, storage.disk_grow_partition, structs-disk_cc7d52cd-b0b6-4e5c-a323-6d513f37e602.xml"
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
-	DISK_GROW_PARTITION
product:
- Windows
targetos: Windows
req.typenames: DISK_GROW_PARTITION, *PDISK_GROW_PARTITION
---

# _DISK_GROW_PARTITION structure


## -description


The DISK_GROW_PARTITION structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560376">IOCTL_DISK_GROW_PARTITION</a> request to enlarge a partition. 


## -struct-fields




### -field PartitionNumber

Specifies a number identifying the partition to be enlarged.


### -field BytesToGrow

Indicates the number of bytes that the partition should be extended by. Note that this value is not the new size of the partition.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560376">IOCTL_DISK_GROW_PARTITION</a>
 

 

