---
UID: NF:ntddk.IoReadPartitionTableEx
title: IoReadPartitionTableEx function
author: windows-driver-content
description: The IoReadPartitionTableEx routine reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition.
old-location: storage\ioreadpartitiontableex.htm
tech.root: storage
ms.assetid: 1aa8665a-1674-4fca-b5c6-d8d25166ca29
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoReadPartitionTableEx, IoReadPartitionTableEx routine [Storage Devices], ntddk/IoReadPartitionTableEx, rtns-disk_eb4e14e1-14a3-441a-b8ff-9ce68c1b3992.xml, storage.ioreadpartitiontableex
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
-	IoReadPartitionTableEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoReadPartitionTableEx function


## -description


The <b>IoReadPartitionTableEx</b> routine reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the disk whose partitions are to be read.


### -param DriveLayout

TBD




#### - PartitionBuffer [out]

Pointer to an uninitialized address. If successful, <b>IoReadPartitionTableEx</b> allocates the memory for this buffer from nonpaged pool and returns the drive layout information in it.


## -returns



This routine returns a value of STATUS_SUCCESS if at least one sector table was read. Otherwise, it returns an error status value and sets the pointer at <i>PartitionBuffer</i> to <b>NULL</b>.




## -remarks



<b>IoReadPartitionTableEx</b> must only be used by disk drivers. Other drivers should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560364">IOCTL_DISK_GET_DRIVE_LAYOUT_EX</a> disk I/O request instead.

<b>IoReadPartitionTableEx</b> is able to read partition table information from GUID Partition Table (GPT) disks as well as legacy Master Boot Record (MBR) disks. Disk device drivers call this routine during driver initialization.

It is the responsibility of the caller to deallocate the <i>PartitionBuffer</i> that was allocated by this routine with <b>ExFreePool</b>.

Note that disk drivers also return and set partition information in response to IRP_MJ_DEVICE_CONTROL requests with the following I/O control codes:


<dl>
<dt>IOCTL_DISK_GET_PARTITION_INFO_EX</dt>
<dt>IOCTL_DISK_SET_PARTITION_INFO_EX</dt>
<dt>IOCTL_DISK_GET_DRIVE_LAYOUT_EX</dt>
<dt>IOCTL_DISK_SET_DRIVE_LAYOUT_EX</dt>
<dt>IOCTL_DISK_GET_DRIVE_GEOMETRY</dt>
</dl>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560357">IOCTL_DISK_GET_DRIVE_GEOMETRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560364">IOCTL_DISK_GET_DRIVE_LAYOUT_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560375">IOCTL_DISK_GET_PARTITION_INFO_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560411">IOCTL_DISK_SET_DRIVE_LAYOUT_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560417">IOCTL_DISK_SET_PARTITION_INFO_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561456">IoSetPartitionInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561470">IoWritePartitionTableEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a>
 

 

