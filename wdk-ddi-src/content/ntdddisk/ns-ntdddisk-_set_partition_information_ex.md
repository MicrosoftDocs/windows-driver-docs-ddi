---
UID: NS:ntdddisk._SET_PARTITION_INFORMATION_EX
title: "_SET_PARTITION_INFORMATION_EX"
author: windows-driver-content
description: SET_PARTITION_INFORMATION_EX is used with the IOCTL IOCTL_DISK_SET_PARTITION_INFO_EX to set information for a specific partition.
old-location: storage\set_partition_information_ex.htm
tech.root: storage
ms.assetid: a30c10d4-5e85-4a59-b262-054a6fdc2fb8
ms.date: 03/29/2018
ms.keywords: "*PSET_PARTITION_INFORMATION_EX, PSET_PARTITION_INFORMATION_EX, PSET_PARTITION_INFORMATION_EX structure pointer [Storage Devices], SET_PARTITION_INFORMATION_EX, SET_PARTITION_INFORMATION_EX structure [Storage Devices], _SET_PARTITION_INFORMATION_EX, ntdddisk/PSET_PARTITION_INFORMATION_EX, ntdddisk/SET_PARTITION_INFORMATION_EX, storage.set_partition_information_ex, structs-disk_5eaa53e2-feaf-404f-a2a8-174ae77bfab5.xml"
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
-	SET_PARTITION_INFORMATION_EX
product:
- Windows
targetos: Windows
req.typenames: SET_PARTITION_INFORMATION_EX, *PSET_PARTITION_INFORMATION_EX
---

# _SET_PARTITION_INFORMATION_EX structure


## -description


<b>SET_PARTITION_INFORMATION_EX</b> is used with the IOCTL <a href="https://msdn.microsoft.com/library/windows/hardware/ff560417">IOCTL_DISK_SET_PARTITION_INFO_EX</a> to set information for a specific partition.


## -struct-fields




### -field PartitionStyle

Takes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a> enumerated value that specifies the type of partition table that contains the partition.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.Mbr

Contains the information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition. This member is valid when <b>PartitionStyle</b> member is set to PARTITION_STYLE_MBR. For a definition of this structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566198">SET_PARTITION_INFORMATION_MBR</a>.


### -field DUMMYUNIONNAME.Gpt

Contains the information for a GUID Partition Table partition that is not held in common with a Master Boot Record partition. This member is valid when <b>PartitionStyle</b> member is set to PARTITION_STYLE_GPT. For a definition of this structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566196">SET_PARTITION_INFORMATION_GPT</a>.


## -remarks



In the case of GPT partitions, any value that can be retrieved from the partition can also be set. In the MBR case, only the partition signature can be set.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560417">IOCTL_DISK_SET_PARTITION_INFO_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566196">SET_PARTITION_INFORMATION_GPT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566198">SET_PARTITION_INFORMATION_MBR</a>
 

 

