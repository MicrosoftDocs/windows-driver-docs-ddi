---
UID: NF:ntddk.IoReadPartitionTableEx
title: IoReadPartitionTableEx function
author: windows-driver-content
description: The IoReadPartitionTableEx routine reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition.
old-location: storage\ioreadpartitiontableex.htm
old-project: storage
ms.assetid: 1aa8665a-1674-4fca-b5c6-d8d25166ca29
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoReadPartitionTableEx function


## -description


The <b>IoReadPartitionTableEx</b> routine reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition. 


## -syntax


````
NTSTATUS IoReadPartitionTableEx(
  _In_  PDEVICE_OBJECT                      DeviceObject,
  _Out_ struct _DRIVE_LAYOUT_INFORMATION_EX **PartitionBuffer
);
````


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



<b>IoReadPartitionTableEx</b> must only be used by disk drivers. Other drivers should use the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_layout_ex.md">IOCTL_DISK_GET_DRIVE_LAYOUT_EX</a> disk I/O request instead.

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

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_set_drive_layout_ex.md">IOCTL_DISK_SET_DRIVE_LAYOUT_EX</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry.md">IOCTL_DISK_GET_DRIVE_GEOMETRY</a>



<a href="..\ntddk\nf-ntddk-iowritepartitiontableex.md">IoWritePartitionTableEx</a>



<a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_layout_ex.md">IOCTL_DISK_GET_DRIVE_LAYOUT_EX</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_partition_info_ex.md">IOCTL_DISK_GET_PARTITION_INFO_EX</a>



<a href="..\ntddk\nf-ntddk-iosetpartitioninformation.md">IoSetPartitionInformation</a>



<a href="..\ntdddisk\ns-ntdddisk-_partition_information_ex.md">PARTITION_INFORMATION_EX</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_set_partition_info_ex.md">IOCTL_DISK_SET_PARTITION_INFO_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IoReadPartitionTableEx routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

