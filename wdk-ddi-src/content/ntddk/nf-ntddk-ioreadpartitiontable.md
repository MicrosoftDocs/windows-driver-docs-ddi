---
UID: NF:ntddk.IoReadPartitionTable
title: IoReadPartitionTable function (ntddk.h)
description: The IoReadPartitionTable routine is obsolete and is provided only to support existing drivers.
old-location: storage\ioreadpartitiontable.htm
tech.root: storage
ms.assetid: f87c74c3-fcb1-4358-ade6-6c0afc0020e2
ms.date: 03/29/2018
keywords: ["IoReadPartitionTable function"]
ms.keywords: IoReadPartitionTable, IoReadPartitionTable routine [Storage Devices], ntddk/IoReadPartitionTable, rtns-disk_9a43d91f-cbb5-4747-bfa9-66da170b0864.xml, storage.ioreadpartitiontable
f1_keywords:
 - "ntddk/IoReadPartitionTable"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoReadPartitionTable
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoReadPartitionTable function


## -description


The <b>IoReadPartitionTable</b> routine is <b>obsolete</b> and is provided only to support existing drivers. New drivers must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreadpartitiontableex">IoReadPartitionTableEx</a>. <b>IoReadPartitionTable</b> reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the disk whose partitions are to be read.


### -param SectorSize [in]

Specifies the size of the sectors on the disk.


### -param ReturnRecognizedPartitions [in]

Indicates whether only recognized partitions or all partition entries should be returned.


### -param PartitionBuffer [out]

Pointer to an uninitialized address. If successful, <b>IoReadPartitionTable</b> allocates the memory for this buffer from nonpaged pool and returns the drive layout information in it.


## -returns



This routine returns a value of STATUS_SUCCESS if at least one sector table was read. Otherwise, it returns an error status and sets the pointer at <i>PartitionBuffer</i> to <b>NULL</b>.




## -remarks



<b>IoReadPartitionTable</b> must only be used by disk drivers. Other drivers should use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_drive_layout">IOCTL_DISK_GET_DRIVE_LAYOUT</a> disk I/O request instead.

Disk device drivers call this routine during driver initialization.

It is the responsibility of the caller to deallocate the <i>PartitionBuffer</i> that was allocated by this routine with <b>ExFreePool</b>.

The algorithm used by this routine is determined by the Boolean value <i>ReturnRecognizedPartitions</i>:

<ul>
<li>
Read each partition table and, for each valid and recognized partition found, fill in an element in an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information">PARTITION_INFORMATION</a> entries. The array of partition information entries is pointed to by the <b>PartitionEntry</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_drive_layout_information">DRIVE_LAYOUT_INFORMATION</a> structure. The DRIVE_LAYOUT_INFORMATION structure is found at the location pointed to by <i>PartitionBuffer</i>. Extended partitions are located in order to find other partition tables, but no entries are built for them.

</li>
</ul>
Read each partition table and, for each and every entry, fill in a partition information entry. Extended partitions are located to find each partition on the disk; entries are built for these as well.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_drive_layout">IOCTL_DISK_GET_DRIVE_LAYOUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_partition_info">IOCTL_DISK_GET_PARTITION_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_set_drive_layout">IOCTL_DISK_SET_DRIVE_LAYOUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iosetpartitioninformation">IoSetPartitionInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iowritepartitiontable">IoWritePartitionTable</a>
 

 

