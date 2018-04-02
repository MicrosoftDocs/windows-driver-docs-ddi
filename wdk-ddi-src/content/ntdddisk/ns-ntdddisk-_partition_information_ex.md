---
UID: NS:ntdddisk._PARTITION_INFORMATION_EX
title: "_PARTITION_INFORMATION_EX"
author: windows-driver-content
description: PARTITION_INFORMATION_EX is the extended version of the PARTITION_INFORMATION structure. It holds information both for partitions with a Master Boot Record and for partitions with a GUID Partition Table.
old-location: storage\partition_information_ex.htm
old-project: storage
ms.assetid: de44fe5a-5d47-4b2e-ab94-52cadfdbc345
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PPARTITION_INFORMATION_EX, PARTITION_INFORMATION_EX, PARTITION_INFORMATION_EX structure [Storage Devices], PPARTITION_INFORMATION_EX, PPARTITION_INFORMATION_EX structure pointer [Storage Devices], _PARTITION_INFORMATION_EX, ntdddisk/PARTITION_INFORMATION_EX, ntdddisk/PPARTITION_INFORMATION_EX, storage.partition_information_ex, structs-disk_459428ff-6869-41c6-b72f-94721018f66e.xml"
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
-	PARTITION_INFORMATION_EX
product: Windows
targetos: Windows
req.typenames: PARTITION_INFORMATION_EX, *PPARTITION_INFORMATION_EX
---

# _PARTITION_INFORMATION_EX structure


## -description


PARTITION_INFORMATION_EX is the extended version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a> structure. It holds information both for partitions with a Master Boot Record and for partitions with a GUID Partition Table.


## -struct-fields




### -field PartitionStyle

Takes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a> enumerated value that specifies the type of partition table that contains the partition.


### -field StartingOffset

Specifies the offset in bytes on drive where the partition begins.


### -field PartitionLength

Specifies the length in bytes of the partition.


### -field PartitionNumber

Specifies the number of the partition.


### -field RewritePartition

Indicates, when <b>TRUE</b>, that the partition information has changed. When <b>FALSE</b>, the information has not changed. This member has a value of <b>TRUE</b> when the partition has changed as a result of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560408">IOCTL_DISK_SET_DRIVE_LAYOUT</a> IOCTL. This informs the system that the partition information needs to be rewritten.


### -field DUMMYUNIONNAME

 




#### - Gpt

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563763">PARTITION_INFORMATION_GPT</a> containing information specific to a partition with a <b>PartitionStyle</b> member of PARTITION_STYLE_GPT.


#### - Mbr

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563767">PARTITION_INFORMATION_MBR</a> containing information specific to a partition with a <b>PartitionStyle</b> member of PARTITION_STYLE_MBR.


## -remarks



This is the extended version of the partition information structure, PARTITION_INFORMATION. <a href="https://msdn.microsoft.com/library/windows/hardware/ff561454">IoReadPartitionTableEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561470">IoWritePartitionTableEx</a> operate on an array of PARTITON_INFORMATION_EX structures contained within the extended drive layout structure, <a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a>. PARTITION_INFORMATION_EX replaces the structure PARTITION_INFORMATION that was used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561464">IoWritePartitionTable</a>. The principal difference is that the new structures and routines support both Master Boot Record (MBR) partitions and GUID Partition Table (GPT) partitions, whereas the older routines and structures are only used with MBR partitions.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561464">IoWritePartitionTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563763">PARTITION_INFORMATION_GPT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563767">PARTITION_INFORMATION_MBR</a>
 

 

