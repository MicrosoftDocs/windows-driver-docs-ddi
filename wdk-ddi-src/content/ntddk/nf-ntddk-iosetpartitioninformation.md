---
UID: NF:ntddk.IoSetPartitionInformation
title: IoSetPartitionInformation function
author: windows-driver-content
description: The IoSetPartitionInformation routine is obsolete and is provided only to support existing drivers.
old-location: storage\iosetpartitioninformation.htm
old-project: storage
ms.assetid: 3f1a6e3f-3bbc-4cc5-8efe-e3cf6ac3adf5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IoSetPartitionInformation, IoSetPartitionInformation routine [Storage Devices], ntddk/IoSetPartitionInformation, rtns-disk_58012dfd-a95d-4af6-a09d-e1a4bcb458e2.xml, storage.iosetpartitioninformation
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
req.irql: PASSIVE_LEVEL (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoSetPartitionInformation
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoSetPartitionInformation function


## -description


The <b>IoSetPartitionInformation</b> routine is <b>obsolete</b> and is provided only to support existing drivers. New drivers must use <a href="..\ntddk\nf-ntddk-iosetpartitioninformationex.md">IoSetPartitionInformationEx</a>. 

<b>IoSetPartitionInformation</b> sets the partition type and number in a partition table entry for the disk represented by <i>DeviceObject</i>.


## -syntax


````
NTSTATUS FASTCALL IoSetPartitionInformation(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ ULONG          SectorSize,
  _In_ ULONG          PartitionNumber,
  _In_ ULONG          PartitionType
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object representing the device on which the partition type is to be set.


### -param SectorSize [in]

Specifies the size, in bytes, of sectors on the disk.


### -param PartitionNumber [in]

Specifies the partition number on the device whose partition type is to be set.


### -param PartitionType [in]

Specifies the type for the partition. For a list of some of the key partition types see <a href="..\ntdddisk\ns-ntdddisk-_partition_information.md">PARTITION_INFORMATION</a>. 


## -returns



If <b>IoSetPartitionInformation</b> returns STATUS_SUCCESS, the disk driver updates its notion of the partition type for this partition in its device extension.




## -remarks



<b>IoSetPartitionInformation</b> must only be used by disk drivers. Other drivers should use the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_set_partition_info.md">IOCTL_DISK_SET_PARTITION_INFO</a> disk I/O request instead.

This routine is called when a disk device driver is asked to set the partition type in a partition table entry by an IRP_MJ_DEVICE_CONTROL request. This request is generally issued by the format utility, which performs I/O control functions on the partition. The driver passes a pointer to the device object representing the physical disk and the number of the partition associated with the device object that the format utility has open. Since the HAL routines that underlie <b>IoSetPartitionInformation</b> were developed before support of dynamic partitioning was implemented, they do not distinguish between the <i>partition ordinal</i> (that is the order of a partition on a disk) and the <i>partition number</i> (the partition number assigned to a partition in order to identify it to the system). Drivers must call <b>IoSetPartitionInformation</b> using the <i>ordinal</i> number of the partition and not the actual partition number.

This routine is synchronous and must be called by the disk driver's Dispatch routine or by a driver thread. Thus, all user and file system threads must be prepared to enter a wait state when issuing the device control request to set the partition type for the device.

This routine operates under the assumption that the partition number passed in by the disk driver actually exists.

This routine must be called at IRQL = PASSIVE_LEVEL because it uses a kernel event object to synchronize I/O completion on the device. The event cannot be set to the Signaled state without queuing and executing the I/O system's special kernel APC routine for I/O completion.




## -see-also

<a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>



<a href="..\ntddk\nf-ntddk-iowritepartitiontable.md">IoWritePartitionTable</a>



<a href="..\ntddk\nf-ntddk-iosetpartitioninformationex.md">IoSetPartitionInformationEx</a>



 

 


