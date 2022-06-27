---
UID: NS:ntdddisk._PARTITION_INFORMATION_EX
title: PARTITION_INFORMATION_EX (ntdddisk.h)
description: PARTITION_INFORMATION_EX is the extended version of the PARTITION_INFORMATION structure. It holds information both for partitions with a Master Boot Record and for partitions with a GUID Partition Table.
old-location: storage\partition_information_ex.htm
tech.root: storage
ms.date: 05/20/2022
keywords: ["PARTITION_INFORMATION_EX structure"]
ms.keywords: "*PPARTITION_INFORMATION_EX, PARTITION_INFORMATION_EX, PARTITION_INFORMATION_EX structure [Storage Devices], PPARTITION_INFORMATION_EX, PPARTITION_INFORMATION_EX structure pointer [Storage Devices], _PARTITION_INFORMATION_EX, ntdddisk/PARTITION_INFORMATION_EX, ntdddisk/PPARTITION_INFORMATION_EX, storage.partition_information_ex, structs-disk_459428ff-6869-41c6-b72f-94721018f66e.xml"
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
targetos: Windows
req.typenames: PARTITION_INFORMATION_EX, *PPARTITION_INFORMATION_EX
f1_keywords:
 - _PARTITION_INFORMATION_EX
 - ntdddisk/_PARTITION_INFORMATION_EX
 - PPARTITION_INFORMATION_EX
 - ntdddisk/PPARTITION_INFORMATION_EX
 - PARTITION_INFORMATION_EX
 - ntdddisk/PARTITION_INFORMATION_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _PARTITION_INFORMATION_EX
 - PPARTITION_INFORMATION_EX
 - PARTITION_INFORMATION_EX
---

# PARTITION_INFORMATION_EX structure

## -description

PARTITION_INFORMATION_EX is the extended version of the [**PARTITION_INFORMATION**](ns-ntdddisk-_partition_information.md) structure. It holds information both for partitions with a Master Boot Record and for partitions with a GUID Partition Table.

## -struct-fields

### -field PartitionStyle

Takes a [**PARTITION_STYLE**](/previous-versions/windows/hardware/drivers/ff563773(v=vs.85)) enumerated value that specifies the type of partition table that contains the partition.

### -field StartingOffset

Specifies the offset in bytes on drive where the partition begins.

### -field PartitionLength

Specifies the length in bytes of the partition.

### -field PartitionNumber

Specifies the number of the partition.

### -field RewritePartition

Indicates, when **TRUE**, that the partition information has changed. When **FALSE**, the information has not changed. This member has a value of **TRUE** when the partition has changed as a result of an [IOCTL_DISK_SET_DRIVE_LAYOUT](ni-ntdddisk-ioctl_disk_set_drive_layout.md) IOCTL. This informs the system that the partition information needs to be rewritten.

### -field IsServicePartition

When **TRUE**, indicates that the partition is service.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.Mbr

Contains a structure of type [PARTITION_INFORMATION_MBR](ns-ntdddisk-_partition_information_mbr.md) containing information specific to a partition with a **PartitionStyle** member of PARTITION_STYLE_MBR.

### -field DUMMYUNIONNAME.Gpt

Contains a structure of type [PARTITION_INFORMATION_GPT](ns-ntdddisk-_partition_information_gpt.md) containing information specific to a partition with a **PartitionStyle** member of PARTITION_STYLE_GPT.

## -remarks

This is the extended version of the partition information structure, PARTITION_INFORMATION. [IoReadPartitionTableEx](../ntddk/nf-ntddk-ioreadpartitiontableex.md) and [IoWritePartitionTableEx](../ntddk/nf-ntddk-iowritepartitiontableex.md) operate on an array of PARTITON_INFORMATION_EX structures contained within the extended drive layout structure, [DRIVE_LAYOUT_INFORMATION_EX](ns-ntdddisk-_drive_layout_information_ex.md). **PARTITION_INFORMATION_EX** replaces the structure **PARTITION_INFORMATION** that was used with [IoReadPartitionTable](../ntddk/nf-ntddk-ioreadpartitiontable.md) and [IoWritePartitionTable](../ntddk/nf-ntddk-iowritepartitiontable.md). The principle difference is that the new structures and routines support both Master Boot Record (MBR) partitions and GUID Partition Table (GPT) partitions, whereas the older routines and structures are only used with MBR partitions.

## -see-also

[IoReadPartitionTable](../ntddk/nf-ntddk-ioreadpartitiontable.md)

[IoWritePartitionTable](../ntddk/nf-ntddk-iowritepartitiontable.md)

[PARTITION_INFORMATION_GPT](ns-ntdddisk-_partition_information_gpt.md)

[PARTITION_INFORMATION_MBR](ns-ntdddisk-_partition_information_mbr.md)
