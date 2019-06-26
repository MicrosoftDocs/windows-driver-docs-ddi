---
UID: NI:ntdddisk.IOCTL_DISK_SET_PARTITION_INFO
title: IOCTL_DISK_SET_PARTITION_INFO (ntdddisk.h)
description: Changes the partition type of the specified disk partition. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_set_partition_info.htm
tech.root: storage
ms.assetid: 3ff5a328-04b0-4de9-abe1-759c36f31899
ms.date: 03/29/2018
ms.keywords: IOCTL_DISK_SET_PARTITION_INFO, IOCTL_DISK_SET_PARTITION_INFO control, IOCTL_DISK_SET_PARTITION_INFO control code [Storage Devices], k307_9035067b-43ed-4b4f-9516-23fd7448d5e6.xml, ntdddisk/IOCTL_DISK_SET_PARTITION_INFO, storage.ioctl_disk_set_partition_info
ms.topic: ioctl
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
- IOCTL_DISK_SET_PARTITION_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_SET_PARTITION_INFO IOCTL


## -description



Changes the partition type of the specified disk partition. (Floppy drivers need not handle this request.)




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_set_partition_information">SET_PARTITION_INFORMATION</a> to be set. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(SET_PARTITION_INFORMATION).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_PARAMETER, STATUS_INVALID_DEVICE_REQUEST, STATUS_UNSUCCESSFUL, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_set_partition_information">SET_PARTITION_INFORMATION</a>
 

 

