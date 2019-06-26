---
UID: NI:ntdddisk.IOCTL_DISK_SET_DRIVE_LAYOUT
title: IOCTL_DISK_SET_DRIVE_LAYOUT (ntdddisk.h)
description: Repartitions a disk as specified. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_set_drive_layout.htm
tech.root: storage
ms.assetid: d6b0682a-bce2-40d3-a69b-cf676c21d253
ms.date: 03/29/2018
ms.keywords: IOCTL_DISK_SET_DRIVE_LAYOUT, IOCTL_DISK_SET_DRIVE_LAYOUT control, IOCTL_DISK_SET_DRIVE_LAYOUT control code [Storage Devices], k307_53d3cc3b-a829-432a-8ee0-9a2035d08a62.xml, ntdddisk/IOCTL_DISK_SET_DRIVE_LAYOUT, storage.ioctl_disk_set_drive_layout
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
- IOCTL_DISK_SET_DRIVE_LAYOUT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_SET_DRIVE_LAYOUT IOCTL


## -description



Repartitions a disk as specified. (Floppy drivers need not handle this request.)




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_drive_layout_information">DRIVE_LAYOUT_INFORMATION</a> values to be set. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(DRIVE_LAYOUT_INFORMATION).


### -output-buffer

Returns updated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_drive_layout_information">DRIVE_LAYOUT_INFORMATION</a>, possibly with modified partition numbers, to the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_drive_layout_information">DRIVE_LAYOUT_INFORMATION</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned information. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_PARAMETER, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_drive_layout_information">DRIVE_LAYOUT_INFORMATION</a>
 

 

