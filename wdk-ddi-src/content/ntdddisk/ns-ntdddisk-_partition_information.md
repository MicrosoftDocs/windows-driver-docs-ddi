---
UID: NS:ntdddisk._PARTITION_INFORMATION
title: "_PARTITION_INFORMATION"
author: windows-driver-content
description: The PARTITION_INFORMATION structure contains partition information for a partition with a traditional AT-style Master Boot Record (MBR).
old-location: storage\partition_information.htm
tech.root: storage
ms.assetid: 06c3ed56-3640-431d-a4f0-bf3228a02cc2
ms.date: 03/29/2018
ms.keywords: "*PPARTITION_INFORMATION, PARTITION_INFORMATION, PARTITION_INFORMATION structure [Storage Devices], PPARTITION_INFORMATION, PPARTITION_INFORMATION structure pointer [Storage Devices], _PARTITION_INFORMATION, ntdddisk/PARTITION_INFORMATION, ntdddisk/PPARTITION_INFORMATION, storage.partition_information, structs-disk_19ff49c5-6929-46fb-a9c2-4850969a99a8.xml"
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
-	PARTITION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PARTITION_INFORMATION, *PPARTITION_INFORMATION
---

# _PARTITION_INFORMATION structure


## -description


The PARTITION_INFORMATION structure contains partition information for a partition with a traditional AT-style Master Boot Record (MBR). 


## -struct-fields




### -field StartingOffset

Specifies the offset in bytes on drive where the partition begins.


### -field PartitionLength

Specifies the length in bytes of the partition. 


### -field HiddenSectors

Specifies the number of hidden sectors. 


### -field PartitionNumber

Specifies the number of the partition.


### -field PartitionType



#####  Possible values are as follows:



#################### 


### -field BootIndicator

Indicates, when <b>TRUE</b>, that this partition is a bootable (active) partition for this device. When <b>FALSE</b>, this partition is not bootable. This member is set according to the partition list entry boot indicator returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a>. 


### -field RecognizedPartition

Indicates, when <b>TRUE</b>, that the system recognized the type of the partition. When <b>FALSE</b>, the system did not recognize the type of the partition. 


### -field RewritePartition

Indicates, when <b>TRUE</b>, that the partition information has changed. When <b>FALSE</b>, the partition information has not changed. This member has a value of <b>TRUE</b> when the partition has changed as a result of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560408">IOCTL_DISK_SET_DRIVE_LAYOUT</a> IOCTL. This informs the system that the partition information needs to be rewritten.


## -remarks



The partition entry data in PARTITION_INFORMATION forms part of the drive layout information reported by the legacy routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a> in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552659">DRIVE_LAYOUT_INFORMATION</a> structure. DRIVE_LAYOUT_INFORMATION contains an array of PARTITION_INFORMATION structures pointed to by its <b>PartitionEntry</b> member. Each partition entry contains information for a partition on the drive. PARTITION_INFORMATION is also used with the legacy routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff561456">IoSetPartitionInformation</a> to change the properties of the partition, such as its type, recorded on the disk. 

In Windows 2000 and later operating systems, disk drivers should use structures <a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a> along with routines <a href="https://msdn.microsoft.com/library/windows/hardware/ff561454">IoReadPartitionTableEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561461">IoSetPartitionInformationEx</a> to read and alter partition information on the disk. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552659">DRIVE_LAYOUT_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561454">IoReadPartitionTableEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561456">IoSetPartitionInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561461">IoSetPartitionInformationEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a>
 

 

