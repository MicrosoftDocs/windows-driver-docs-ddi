---
UID: NS:ntdddisk._PARTITION_INFORMATION_EX
title: "_PARTITION_INFORMATION_EX"
author: windows-driver-content
description: PARTITION_INFORMATION_EX is the extended version of the PARTITION_INFORMATION structure. It holds information both for partitions with a Master Boot Record and for partitions with a GUID Partition Table.
old-location: storage\partition_information_ex.htm
old-project: storage
ms.assetid: de44fe5a-5d47-4b2e-ab94-52cadfdbc345
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PPARTITION_INFORMATION_EX, PARTITION_INFORMATION_EX structure [Storage Devices], _PARTITION_INFORMATION_EX, *PPARTITION_INFORMATION_EX, ntdddisk/PARTITION_INFORMATION_EX, structs-disk_459428ff-6869-41c6-b72f-94721018f66e.xml, ntdddisk/PPARTITION_INFORMATION_EX, PPARTITION_INFORMATION_EX structure pointer [Storage Devices], PARTITION_INFORMATION_EX, storage.partition_information_ex
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
-	PARTITION_INFORMATION_EX
product: Windows
targetos: Windows
req.typenames: PARTITION_INFORMATION_EX, *PPARTITION_INFORMATION_EX
---

# _PARTITION_INFORMATION_EX structure


## -description


PARTITION_INFORMATION_EX is the extended version of the <a href="..\ntdddisk\ns-ntdddisk-_partition_information.md">PARTITION_INFORMATION</a> structure. It holds information both for partitions with a Master Boot Record and for partitions with a GUID Partition Table.


## -syntax


````
typedef struct _PARTITION_INFORMATION_EX {
  PARTITION_STYLE PartitionStyle;
  LARGE_INTEGER   StartingOffset;
  LARGE_INTEGER   PartitionLength;
  ULONG           PartitionNumber;
  BOOLEAN         RewritePartition;
  union {
    PARTITION_INFORMATION_MBR Mbr;
    PARTITION_INFORMATION_GPT Gpt;
  };
} PARTITION_INFORMATION_EX, *PPARTITION_INFORMATION_EX;
````


## -struct-fields




### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.Mbr

 


### -field DUMMYUNIONNAME.Gpt

 


### -field PartitionStyle

Takes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a> enumerated value that specifies the type of partition table that contains the partition.


### -field StartingOffset

Specifies the offset in bytes on drive where the partition begins.


### -field PartitionLength

Specifies the length in bytes of the partition.


### -field PartitionNumber

Specifies the number of the partition.


### -field RewritePartition

Indicates, when <b>TRUE</b>, that the partition information has changed. When <b>FALSE</b>, the information has not changed. This member has a value of <b>TRUE</b> when the partition has changed as a result of an <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_set_drive_layout.md">IOCTL_DISK_SET_DRIVE_LAYOUT</a> IOCTL. This informs the system that the partition information needs to be rewritten.


#### - Mbr

Contains a structure of type <a href="..\ntdddisk\ns-ntdddisk-_partition_information_mbr.md">PARTITION_INFORMATION_MBR</a> containing information specific to a partition with a <b>PartitionStyle</b> member of PARTITION_STYLE_MBR.


#### - Gpt

Contains a structure of type <a href="..\ntdddisk\ns-ntdddisk-_partition_information_gpt.md">PARTITION_INFORMATION_GPT</a> containing information specific to a partition with a <b>PartitionStyle</b> member of PARTITION_STYLE_GPT.


## -remarks


This is the extended version of the partition information structure, PARTITION_INFORMATION. <a href="..\ntddk\nf-ntddk-ioreadpartitiontableex.md">IoReadPartitionTableEx</a> and <a href="..\ntddk\nf-ntddk-iowritepartitiontableex.md">IoWritePartitionTableEx</a> operate on an array of PARTITON_INFORMATION_EX structures contained within the extended drive layout structure, <a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a>. PARTITION_INFORMATION_EX replaces the structure PARTITION_INFORMATION that was used with <a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a> and <a href="..\ntddk\nf-ntddk-iowritepartitiontable.md">IoWritePartitionTable</a>. The principal difference is that the new structures and routines support both Master Boot Record (MBR) partitions and GUID Partition Table (GPT) partitions, whereas the older routines and structures are only used with MBR partitions.



## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_partition_information_gpt.md">PARTITION_INFORMATION_GPT</a>

<a href="..\ntddk\nf-ntddk-iowritepartitiontable.md">IoWritePartitionTable</a>

<a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>

<a href="..\ntdddisk\ns-ntdddisk-_partition_information_mbr.md">PARTITION_INFORMATION_MBR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PARTITION_INFORMATION_EX structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

