---
UID: NS:ntdddisk._PARTITION_INFORMATION
title: "_PARTITION_INFORMATION"
author: windows-driver-content
description: The PARTITION_INFORMATION structure contains partition information for a partition with a traditional AT-style Master Boot Record (MBR).
old-location: storage\partition_information.htm
old-project: storage
ms.assetid: 06c3ed56-3640-431d-a4f0-bf3228a02cc2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: structs-disk_19ff49c5-6929-46fb-a9c2-4850969a99a8.xml, PARTITION_INFORMATION structure [Storage Devices], ntdddisk/PPARTITION_INFORMATION, ntdddisk/PARTITION_INFORMATION, storage.partition_information, _PARTITION_INFORMATION, PPARTITION_INFORMATION, PPARTITION_INFORMATION structure pointer [Storage Devices], PARTITION_INFORMATION, *PPARTITION_INFORMATION
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
-	PARTITION_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PPARTITION_INFORMATION, PARTITION_INFORMATION"
---

# _PARTITION_INFORMATION structure


## -description


The PARTITION_INFORMATION structure contains partition information for a partition with a traditional AT-style Master Boot Record (MBR). 


## -syntax


````
typedef struct _PARTITION_INFORMATION {
  LARGE_INTEGER StartingOffset;
  LARGE_INTEGER PartitionLength;
  ULONG         HiddenSectors;
  ULONG         PartitionNumber;
  UCHAR         PartitionType;
  BOOLEAN       BootIndicator;
  BOOLEAN       RecognizedPartition;
  BOOLEAN       RewritePartition;
} PARTITION_INFORMATION, *PPARTITION_INFORMATION;
````


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

Indicates, when <b>TRUE</b>, that this partition is a bootable (active) partition for this device. When <b>FALSE</b>, this partition is not bootable. This member is set according to the partition list entry boot indicator returned by <a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>. 


### -field RecognizedPartition

Indicates, when <b>TRUE</b>, that the system recognized the type of the partition. When <b>FALSE</b>, the system did not recognize the type of the partition. 


### -field RewritePartition

Indicates, when <b>TRUE</b>, that the partition information has changed. When <b>FALSE</b>, the partition information has not changed. This member has a value of <b>TRUE</b> when the partition has changed as a result of an <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_set_drive_layout.md">IOCTL_DISK_SET_DRIVE_LAYOUT</a> IOCTL. This informs the system that the partition information needs to be rewritten.


## -remarks



The partition entry data in PARTITION_INFORMATION forms part of the drive layout information reported by the legacy routine <a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a> in the <a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information.md">DRIVE_LAYOUT_INFORMATION</a> structure. DRIVE_LAYOUT_INFORMATION contains an array of PARTITION_INFORMATION structures pointed to by its <b>PartitionEntry</b> member. Each partition entry contains information for a partition on the drive. PARTITION_INFORMATION is also used with the legacy routine <a href="..\ntddk\nf-ntddk-iosetpartitioninformation.md">IoSetPartitionInformation</a> to change the properties of the partition, such as its type, recorded on the disk. 

In Windows 2000 and later operating systems, disk drivers should use structures <a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a> and <a href="..\ntdddisk\ns-ntdddisk-_partition_information_ex.md">PARTITION_INFORMATION_EX</a> along with routines <a href="..\ntddk\nf-ntddk-ioreadpartitiontableex.md">IoReadPartitionTableEx</a> and <a href="..\ntddk\nf-ntddk-iosetpartitioninformationex.md">IoSetPartitionInformationEx</a> to read and alter partition information on the disk. 




## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a>



<a href="..\ntddk\nf-ntddk-iosetpartitioninformationex.md">IoSetPartitionInformationEx</a>



<a href="..\ntddk\nf-ntddk-iosetpartitioninformationex.md">IoSetPartitionInformationEx</a>



<a href="..\ntdddisk\ns-ntdddisk-_partition_information_ex.md">PARTITION_INFORMATION_EX</a>



<a href="..\ntdddisk\ns-ntdddisk-_partition_information_ex.md">PARTITION_INFORMATION_EX</a>



<a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>



<a href="..\ntddk\nf-ntddk-ioreadpartitiontableex.md">IoReadPartitionTableEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PARTITION_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

