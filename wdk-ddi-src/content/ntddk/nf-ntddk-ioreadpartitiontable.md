---
UID: NF:ntddk.IoReadPartitionTable
title: IoReadPartitionTable function
author: windows-driver-content
description: The IoReadPartitionTable routine is obsolete and is provided only to support existing drivers.
old-location: storage\ioreadpartitiontable.htm
old-project: storage
ms.assetid: f87c74c3-fcb1-4358-ade6-6c0afc0020e2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoReadPartitionTable, IoReadPartitionTable routine [Storage Devices], ntddk/IoReadPartitionTable, rtns-disk_9a43d91f-cbb5-4747-bfa9-66da170b0864.xml, storage.ioreadpartitiontable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoReadPartitionTable
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoReadPartitionTable function


## -description


The <b>IoReadPartitionTable</b> routine is <b>obsolete</b> and is provided only to support existing drivers. New drivers must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561454">IoReadPartitionTableEx</a>. <b>IoReadPartitionTable</b> reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition. 


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



<b>IoReadPartitionTable</b> must only be used by disk drivers. Other drivers should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560361">IOCTL_DISK_GET_DRIVE_LAYOUT</a> disk I/O request instead.

Disk device drivers call this routine during driver initialization.

It is the responsibility of the caller to deallocate the <i>PartitionBuffer</i> that was allocated by this routine with <b>ExFreePool</b>.

The algorithm used by this routine is determined by the Boolean value <i>ReturnRecognizedPartitions</i>:

<ul>
<li>
Read each partition table and, for each valid and recognized partition found, fill in an element in an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a> entries. The array of partition information entries is pointed to by the <b>PartitionEntry</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552659">DRIVE_LAYOUT_INFORMATION</a> structure. The DRIVE_LAYOUT_INFORMATION structure is found at the location pointed to by <i>PartitionBuffer</i>. Extended partitions are located in order to find other partition tables, but no entries are built for them.

</li>
</ul>
Read each partition table and, for each and every entry, fill in a partition information entry. Extended partitions are located to find each partition on the disk; entries are built for these as well.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560361">IOCTL_DISK_GET_DRIVE_LAYOUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560373">IOCTL_DISK_GET_PARTITION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560408">IOCTL_DISK_SET_DRIVE_LAYOUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561456">IoSetPartitionInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561464">IoWritePartitionTable</a>
 

 

