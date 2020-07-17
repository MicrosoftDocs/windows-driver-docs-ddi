---
UID: NI:ntdddisk.IOCTL_DISK_GROW_PARTITION
title: IOCTL_DISK_GROW_PARTITION (ntdddisk.h)
description: Increases the size of an existing partition.
old-location: storage\ioctl_disk_grow_partition.htm
tech.root: storage
ms.assetid: 984e9e7a-c135-4a6a-973d-b8597d9f8fed
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_GROW_PARTITION IOCTL"]
ms.keywords: IOCTL_DISK_GROW_PARTITION, IOCTL_DISK_GROW_PARTITION control, IOCTL_DISK_GROW_PARTITION control code [Storage Devices], k307_f3c07ac5-6895-46f9-85ad-7706661164a1.xml, ntdddisk/IOCTL_DISK_GROW_PARTITION, storage.ioctl_disk_grow_partition
f1_keywords:
 - "ntdddisk/IOCTL_DISK_GROW_PARTITION"
 - "IOCTL_DISK_GROW_PARTITION"
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
- Ntdddisk.h
api_name:
- IOCTL_DISK_GROW_PARTITION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_GROW_PARTITION IOCTL


## -description



Increases the size of an existing partition. It is used in conjunction with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_update_drive_size">IOCTL_DISK_UPDATE_DRIVE_SIZE</a> to extend a disk, so that it will contain a new free space area, and then to extend an existing partition on the disk into the newly attached free space. It takes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_grow_partition">DISK_GROW_PARTITION</a> structure as the only parameter. For this operation to work, the space after the specified partition must be free. A partition cannot be extended over another existing partition.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_grow_partition">DISK_GROW_PARTITION</a> values - that will be used to increase the size of the partition. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be >= <b>sizeof</b>(DISK_GROW_PARTITION). Otherwise, the driver returns with an error status of STATUS_BUFFER_TOO_SMALL.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_INVALID_PARAMETER, STATUS_UNSUCCESSFUL, or STATUS_DRIVER_INTERNAL_ERROR.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_grow_partition">DISK_GROW_PARTITION</a>
 

 

