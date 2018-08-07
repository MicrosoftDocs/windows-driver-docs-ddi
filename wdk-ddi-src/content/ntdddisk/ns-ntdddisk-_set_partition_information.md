---
UID: NS:ntdddisk._SET_PARTITION_INFORMATION
title: "_SET_PARTITION_INFORMATION"
author: windows-driver-content
description: SET_PARTITION_INFORMATION is used with IOCTL_DISK_SET_PARTITION_INFO to change the partition type of a specified Master Boot Record (MBR) disk partition.
old-location: storage\set_partition_information.htm
tech.root: storage
ms.assetid: 882aedda-5ed5-43e0-a370-59a7c7e4c802
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSET_PARTITION_INFORMATION, PSET_PARTITION_INFORMATION, PSET_PARTITION_INFORMATION structure pointer [Storage Devices], SET_PARTITION_INFORMATION, SET_PARTITION_INFORMATION structure [Storage Devices], SET_PARTITION_INFORMATION_MBR, _SET_PARTITION_INFORMATION, ntdddisk/PSET_PARTITION_INFORMATION, ntdddisk/SET_PARTITION_INFORMATION, storage.set_partition_information, structs-disk_b8b3121b-0001-4c1d-ac4d-1eeb1ce79dd3.xml"
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
-	SET_PARTITION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: SET_PARTITION_INFORMATION, *PSET_PARTITION_INFORMATION
---

# _SET_PARTITION_INFORMATION structure


## -description


SET_PARTITION_INFORMATION is used with IOCTL_DISK_SET_PARTITION_INFO to change the partition type of a specified Master Boot Record (MBR) disk partition.


## -struct-fields




### -field PartitionType

Indicates the partition type. IOCTL_DISK_SET_PARTITION_INFO uses this value to set the partition type. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a> for a list of system-defined GPT partition types.


## -remarks



The single byte unsigned value, <i>PartitionType</i>, contained in this structure defines a traditional AT Master Boot Record style of partition and cannot be used to define an Extensible Firmware Interface partition (also known as a GUID Partition Table partition). GPT partitions use a GUID to indicate the partition type.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560413">IOCTL_DISK_SET_PARTITION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566194">SET_PARTITION_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566196">SET_PARTITION_INFORMATION_GPT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566198">SET_PARTITION_INFORMATION_MBR</a>
 

 

