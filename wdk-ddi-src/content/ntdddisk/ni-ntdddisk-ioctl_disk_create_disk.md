---
UID: NI:ntdddisk.IOCTL_DISK_CREATE_DISK
title: IOCTL_DISK_CREATE_DISK (ntdddisk.h)
description: Creates an empty partition for the device object.
old-location: storage\ioctl_disk_create_disk.htm
tech.root: storage
ms.assetid: 9ec6835c-43b8-4878-9ddf-1ca7c24435c2
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_CREATE_DISK IOCTL"]
ms.keywords: IOCTL_DISK_CREATE_DISK, IOCTL_DISK_CREATE_DISK control, IOCTL_DISK_CREATE_DISK control code [Storage Devices], k307_1520ab81-e89f-4531-a6ac-0998e1b1b658.xml, ntdddisk/IOCTL_DISK_CREATE_DISK, storage.ioctl_disk_create_disk
f1_keywords:
 - "ntdddisk/IOCTL_DISK_CREATE_DISK"
 - "IOCTL_DISK_CREATE_DISK"
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
- IOCTL_DISK_CREATE_DISK
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_CREATE_DISK IOCTL


## -description



Creates an empty partition for the device object. It can operate on either an EFI disk or an MBR disk. The parameters necessary to create an empty disk depend on the type of partition table that will be put onto the disk. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_create_disk">CREATE_DISK</a>.

Disk drivers enumerate partitions as though they were child devices. Thus, upon creating the new partition, the disk class driver notifies the PnP manager by means of a call to <b>IoInvalidateDeviceRelations</b> that the disk device has a new child device (partition).




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the CREATE_DISK data. 


### -input-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be >= <b>sizeof</b>(CREATE_DISK). Otherwise, the driver returns with an error status of STATUS_INFO_LENGTH_MISMATCH.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS if the operation was successful. Other possible status values are: STATUS_NOT_SUPPORTED if the partition style requested is not supported; STATUS_DEVICE_NOT_READY if the class driver failed to retrieve the disk geometry; and STATUS_INSUFFICIENT_RESOURCES if the class driver failed to obtain a necessary resource, such as heap memory.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_create_disk">CREATE_DISK</a>
 

 

