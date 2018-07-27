---
UID: NS:ntdddisk._PARTITION_INFORMATION_MBR
title: "_PARTITION_INFORMATION_MBR"
author: windows-driver-content
description: PARTITION_INFORMATION_MBR contains information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition.
old-location: storage\partition_information_mbr.htm
tech.root: storage
ms.assetid: 846f3a1c-ee0a-42d2-bdf1-7bf09406c955
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PPARTITION_INFORMATION_MBR, PARTITION_INFORMATION_MBR, PARTITION_INFORMATION_MBR structure [Storage Devices], PPARTITION_INFORMATION_MBR, PPARTITION_INFORMATION_MBR structure pointer [Storage Devices], _PARTITION_INFORMATION_MBR, ntdddisk/PARTITION_INFORMATION_MBR, ntdddisk/PPARTITION_INFORMATION_MBR, storage.partition_information_mbr, structs-disk_c386ea16-c8d7-4a5e-8e61-d8e8ddead136.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntddk.h, Ntdddisk.h
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
-	PARTITION_INFORMATION_MBR
product:
- Windows
targetos: Windows
req.typenames: PARTITION_INFORMATION_MBR, *PPARTITION_INFORMATION_MBR
---

# _PARTITION_INFORMATION_MBR structure


## -description


PARTITION_INFORMATION_MBR contains information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition.


## -struct-fields




### -field PartitionType

Specifies the partition type. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a> for a list of system-defined partition types.


### -field BootIndicator

Indicates, when <b>TRUE</b>, that the partition is bootable. When <b>FALSE</b>, the partition is not bootable.


### -field RecognizedPartition

Indicates, when <b>TRUE</b>, that this is a partition with a recognized partition type. When <b>FALSE</b> this is a not a partition with a recognized partition.


### -field HiddenSectors

Contains the number of hidden sectors in the partition.


### -field PartitionId

 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563763">PARTITION_INFORMATION_GPT</a>
 

 

