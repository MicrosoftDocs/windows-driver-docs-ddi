---
UID: NF:ntddk.IoWritePartitionTable
title: IoWritePartitionTable function (ntddk.h)
description: The IoWritePartitionTable routine is obsolete and is provided only to support existing drivers.
old-location: storage\iowritepartitiontable.htm
tech.root: storage
ms.assetid: 406508b2-7509-4d2b-ac22-63644eedcec0
ms.date: 03/29/2018
keywords: ["IoWritePartitionTable function"]
ms.keywords: IoWritePartitionTable, IoWritePartitionTable routine [Storage Devices], ntddk/IoWritePartitionTable, rtns-disk_9358ac66-e3ba-43c0-856f-0f8b4c0ee832.xml, storage.iowritepartitiontable
f1_keywords:
 - "ntddk/IoWritePartitionTable"
 - "IoWritePartitionTable"
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
- IoWritePartitionTable
targetos: Windows
req.typenames: 
---

# IoWritePartitionTable function


## -description


The <b>IoWritePartitionTable</b> routine is <b>obsolete</b> and is provided only to support existing drivers. New drivers must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iowritepartitiontableex">IoWritePartitionTableEx</a>.

<b>IoWritePartitionTable</b> writes partition tables from the entries in the partition list buffer for each partition on the disk represented by the given device object.


## -parameters




### -param DeviceObject 
[in]
Pointer to the device object representing the disk whose partition tables are to be written.


### -param SectorSize 
[in]
Specifies the size in bytes of sectors on the device.


### -param SectorsPerTrack 
[in]
Specifies the track size on the device.


### -param NumberOfHeads 
[in]
Specifies the number of tracks per cylinder.


### -param PartitionBuffer 
[in]
Pointer to the drive layout buffer that contains the partition list entries. For more detailed information see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_drive_layout_information">DRIVE_LAYOUT_INFORMATION</a>.


## -returns



<b>IoWritePartitionTablo</b> returns a status code of STATUS_SUCCESS if all writes were completed without error. In case of failure, the error codes returned by <b>IoWritePartitionTable</b> might include, but are not limited to, the following list:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
Indicates a failure read the correct disk geometry.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates a failure to allocate necessary resources (for example, heap memory, IRPs, etc.).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that sector zero did not have the expected MBR disk signature.

</td>
</tr>
</table>
 




## -remarks



<b>IoWritePartitionTable</b> must only be used by disk drivers. Other drivers should use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_set_drive_layout">IOCTL_DISK_SET_DRIVE_LAYOUT</a> disk I/O request instead.

<b>IoWritePartitionTable</b> is called when a disk device driver is requested to set the partition type in a partition table entry or to repartition the disk by an IRP_MJ_DEVICE_CONTROL request. The device control request is generally issued by the format utility, which performs I/O control functions on the partitions and disks in the machine.

To reset a partition type, the driver passes a pointer to the device object representing the physical disk and the number of the partition associated with the device object that the format utility has open. When a disk is to be repartitioned dynamically, the disk driver must tear down its set of device objects representing the current disk partitions and create a new set of device objects representing the new partitions on the disk.

Applications that create and delete partitions and require full descriptions of the system should call <b>IoReadPartitionTable</b> with <i>ReturnRecognizedPartitions</i> set to <b>FALSE</b>. The drive layout structure can be modified by the system format utility to reflect a new configuration of the disk.

<b>IoWritePartitionTable</b> is synchronous. It must be called by the disk driver's Dispatch routine or by a driver thread. Thus, all user and file system threads must be prepared to enter a wait state when issuing the device control request to reset partition types for the device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreadpartitiontable">IoReadPartitionTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iosetpartitioninformation">IoSetPartitionInformation</a>
 

 

