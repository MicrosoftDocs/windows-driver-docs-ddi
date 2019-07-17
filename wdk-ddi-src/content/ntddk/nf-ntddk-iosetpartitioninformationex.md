---
UID: NF:ntddk.IoSetPartitionInformationEx
title: IoSetPartitionInformationEx function (ntddk.h)
description: For the disk represented by DeviceObject, the IoSetPartitionInformationEx routine initializes a partition table entry with the information specified in the SET_PARTITION_INFORMATION_EX structure.
old-location: storage\iosetpartitioninformationex.htm
tech.root: storage
ms.assetid: e663a9aa-ed83-4d85-b110-390f0c03a724
ms.date: 03/29/2018
ms.keywords: IoSetPartitionInformationEx, IoSetPartitionInformationEx routine [Storage Devices], ntddk/IoSetPartitionInformationEx, rtns-disk_7fd49999-70b3-4d59-b281-ff24b8a22a30.xml, storage.iosetpartitioninformationex
ms.topic: function
f1_keywords:
 - "ntddk/IoSetPartitionInformationEx"
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
req.irql: PASSIVE_LEVEL (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoSetPartitionInformationEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetPartitionInformationEx function


## -description


For the disk represented by <i>DeviceObject</i>, the <b>IoSetPartitionInformationEx</b> routine initializes a partition table entry with the information specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_set_partition_information_ex">SET_PARTITION_INFORMATION_EX</a> structure.


## -parameters




### -param DeviceObject [in]

Pointer to the device object representing the device on which the partition type is to be set.


### -param PartitionNumber [in]

Specifies the partition number on the device whose partition type is to be set.


### -param PartitionInfo [in]

A structure whose <i>PartitionType</i> member specifies the type for the partition. For the currently defined <i>PartitionType</i> values <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_partition_information">PARTITION_INFORMATION</a>.


## -returns



If <b>IoSetPartitionInformationEx</b> returns STATUS_SUCCESS, the disk driver updates its notion of the partition type for this partition in its device extension.




## -remarks



<b>IoSetPartitionInformationEx</b> must only be used by disk drivers. Other drivers should use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ni-ntdddisk-ioctl_disk_set_partition_info_ex">IOCTL_DISK_SET_PARTITION_INFO_EX</a> disk I/O request instead.

This routine is called when a disk device driver is requested to set partition information in a partition table entry by an IRP_MJ_DEVICE_CONTROL request. This request is generally issued by the format utility, which performs I/O control functions on the partition. The driver passes a pointer to the device object representing the physical disk and the number of the partition associated with the device object that the format utility has open. Since the HAL routines that underlie <b>IoSetPartitionInformationEx</b> were developed before support for dynamic partitioning was implemented, they do not distinguish between the <i>partitionordinal</i> (that is the order of a partition on a disk) and the <i>partition number</i> (the partition number assigned to a partition in order to identify it to the system). Drivers must call <b>IoSetPartitionInformationEx</b> using the <i>ordinal</i> number of the partition and not the actual partition number.

If the partition is a Master Boot Record (MBR) type partition, <b>IoSetPartitionInformationEx</b> is limited to setting the partition style, and the partition style, which is represented as an unsigned character. See SET_PARTITION_INFORMATION_MBR for further information about these values.

If the partition is a GUID Partition Table (GPT) partition, <b>IoSetPartitionInformationEx</b> sets the following values: the partition style, the partition type, represented by a GUID instead of an integer as was the case with MBR partitions; a partition ID, also represented by a GUID; a set of attributes (see the Extensible Firmware Interface for a description of these attributes); and a Unicode name for the partition. See <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566196(v=vs.85)">SET_PARTITION_INFORMATION_GPT</a> for further information about these values.

This routine is synchronous and must be called by the disk driver's Dispatch routine or by a driver thread. Thus, all user and file system threads must be prepared to enter a wait state when issuing the device control request to set the partition type for the device.

This routine operates under the assumption that the partition number passed in by the disk driver actually exists.

This routine must be called at IRQL = PASSIVE_LEVEL because it uses a kernel event object to synchronize I/O completion on the device. The event cannot be set to the Signaled state without queuing and executing the I/O system's special kernel APC routine for I/O completion.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-ioreadpartitiontable">IoReadPartitionTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iosetpartitioninformation">IoSetPartitionInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iowritepartitiontable">IoWritePartitionTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_set_partition_information">SET_PARTITION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_set_partition_information_ex">SET_PARTITION_INFORMATION_EX</a>
 

 

