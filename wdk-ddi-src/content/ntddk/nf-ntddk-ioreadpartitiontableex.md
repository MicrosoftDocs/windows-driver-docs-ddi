---
UID: NF:ntddk.IoReadPartitionTableEx
title: IoReadPartitionTableEx function (ntddk.h)
description: The IoReadPartitionTableEx routine reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition.
old-location: storage\ioreadpartitiontableex.htm
tech.root: storage
ms.assetid: 1aa8665a-1674-4fca-b5c6-d8d25166ca29
ms.date: 03/29/2018
keywords: ["IoReadPartitionTableEx function"]
ms.keywords: IoReadPartitionTableEx, IoReadPartitionTableEx routine [Storage Devices], ntddk/IoReadPartitionTableEx, rtns-disk_eb4e14e1-14a3-441a-b8ff-9ce68c1b3992.xml, storage.ioreadpartitiontableex
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IoReadPartitionTableEx
 - ntddk/IoReadPartitionTableEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoReadPartitionTableEx
---

# IoReadPartitionTableEx function


## -description

The <b>IoReadPartitionTableEx</b> routine reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition.

## -parameters

### -param DeviceObject 

[in]
Pointer to the device object for the disk whose partitions are to be read.

### -param DriveLayout

<p>Pointer to an uninitialized address. If successful, <b>IoReadPartitionTableEx</b> allocates the memory for this buffer from nonpaged pool and returns the drive layout information in it.</p>

## -returns

This routine returns a value of STATUS_SUCCESS if at least one sector table was read. Otherwise, it returns an error status value and sets the pointer at <i>PartitionBuffer</i> to <b>NULL</b>.

## -remarks

<b>IoReadPartitionTableEx</b> must only be used by disk drivers. Other drivers should use the <a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_drive_layout_ex">IOCTL_DISK_GET_DRIVE_LAYOUT_EX</a> disk I/O request instead.

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

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_drive_layout_information_ex">DRIVE_LAYOUT_INFORMATION_EX</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_drive_geometry">IOCTL_DISK_GET_DRIVE_GEOMETRY</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_drive_layout_ex">IOCTL_DISK_GET_DRIVE_LAYOUT_EX</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_partition_info_ex">IOCTL_DISK_GET_PARTITION_INFO_EX</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_set_drive_layout_ex">IOCTL_DISK_SET_DRIVE_LAYOUT_EX</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_set_partition_info_ex">IOCTL_DISK_SET_PARTITION_INFO_EX</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iosetpartitioninformation">IoSetPartitionInformation</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iowritepartitiontableex">IoWritePartitionTableEx</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information_ex">PARTITION_INFORMATION_EX</a>