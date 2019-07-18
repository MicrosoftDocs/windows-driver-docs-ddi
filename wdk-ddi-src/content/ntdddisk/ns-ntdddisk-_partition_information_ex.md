---
UID: NS:ntdddisk._PARTITION_INFORMATION_EX
title: _PARTITION_INFORMATION_EX (ntdddisk.h)
description: PARTITION_INFORMATION_EX is the extended version of the PARTITION_INFORMATION structure. It holds information both for partitions with a Master Boot Record and for partitions with a GUID Partition Table.
old-location: storage\partition_information_ex.htm
tech.root: storage
ms.assetid: de44fe5a-5d47-4b2e-ab94-52cadfdbc345
ms.date: 03/29/2018
ms.keywords: "*PPARTITION_INFORMATION_EX, PARTITION_INFORMATION_EX, PARTITION_INFORMATION_EX structure [Storage Devices], PPARTITION_INFORMATION_EX, PPARTITION_INFORMATION_EX structure pointer [Storage Devices], _PARTITION_INFORMATION_EX, ntdddisk/PARTITION_INFORMATION_EX, ntdddisk/PPARTITION_INFORMATION_EX, storage.partition_information_ex, structs-disk_459428ff-6869-41c6-b72f-94721018f66e.xml"
ms.topic: struct
f1_keywords:
 - "ntdddisk/PARTITION_INFORMATION_EX"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntdddisk.h
api_name:
- PARTITION_INFORMATION_EX
product:
- Windows
targetos: Windows
req.typenames: PARTITION_INFORMATION_EX, *PPARTITION_INFORMATION_EX
---

# _PARTITION_INFORMATION_EX structure

## -description

PARTITION_INFORMATION_EX is the extended version of the [PARTITION_INFORMATION](ns-ntdddisk-_partition_information.md) structure. It holds information both for partitions with a Master Boot Record and for partitions with a GUID Partition Table.

## -struct-fields

### -field PartitionStyle

Takes a [PARTITION_STYLE](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff563773(v=vs.85)) enumerated value that specifies the type of partition table that contains the partition.

### -field StartingOffset

Specifies the offset in bytes on drive where the partition begins.

### -field PartitionLength

Specifies the length in bytes of the partition.

### -field PartitionNumber

Specifies the number of the partition.

### -field RewritePartition

Indicates, when **TRUE**, that the partition information has changed. When **FALSE**, the information has not changed. This member has a value of **TRUE** when the partition has changed as a result of an [IOCTL_DISK_SET_DRIVE_LAYOUT](ni-ntdddisk-ioctl_disk_set_drive_layout.md) IOCTL. This informs the system that the partition information needs to be rewritten.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.Mbr

Contains a structure of type [PARTITION_INFORMATION_MBR](ns-ntdddisk-_partition_information_mbr.md) containing information specific to a partition with a **PartitionStyle** member of PARTITION_STYLE_MBR.

### -field DUMMYUNIONNAME.Gpt

Contains a structure of type [PARTITION_INFORMATION_GPT](ns-ntdddisk-_partition_information_gpt.md) containing information specific to a partition with a **PartitionStyle** member of PARTITION_STYLE_GPT.

## -remarks

This is the extended version of the partition information structure, PARTITION_INFORMATION. [IoReadPartitionTableEx](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-ioreadpartitiontableex) and [IoWritePartitionTableEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iowritepartitiontableex) operate on an array of PARTITON_INFORMATION_EX structures contained within the extended drive layout structure, [DRIVE_LAYOUT_INFORMATION_EX](ns-ntdddisk-_drive_layout_information_ex.md). **PARTITION_INFORMATION_EX** replaces the structure **PARTITION_INFORMATION** that was used with [IoReadPartitionTable](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-ioreadpartitiontable) and [IoWritePartitionTable](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iowritepartitiontable). The principle difference is that the new structures and routines support both Master Boot Record (MBR) partitions and GUID Partition Table (GPT) partitions, whereas the older routines and structures are only used with MBR partitions.

## -see-also

[IoReadPartitionTable](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-ioreadpartitiontable)

[IoWritePartitionTable](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iowritepartitiontable)

[PARTITION_INFORMATION_GPT](ns-ntdddisk-_partition_information_gpt.md)

[PARTITION_INFORMATION_MBR](ns-ntdddisk-_partition_information_mbr.md)
