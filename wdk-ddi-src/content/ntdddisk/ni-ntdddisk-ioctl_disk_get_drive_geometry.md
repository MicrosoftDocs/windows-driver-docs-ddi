---
UID: NI:ntdddisk.IOCTL_DISK_GET_DRIVE_GEOMETRY
title: IOCTL_DISK_GET_DRIVE_GEOMETRY (ntdddisk.h)
description: Returns information about the physical disk's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).
old-location: storage\ioctl_disk_get_drive_geometry.htm
tech.root: storage
ms.assetid: 571308bc-1e8e-437a-8819-8b28251a3f03
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_GET_DRIVE_GEOMETRY IOCTL"]
ms.keywords: IOCTL_DISK_GET_DRIVE_GEOMETRY, IOCTL_DISK_GET_DRIVE_GEOMETRY control, IOCTL_DISK_GET_DRIVE_GEOMETRY control code [Storage Devices], k307_e6bc4a05-f2cf-40f7-9632-b78da2087662.xml, ntdddisk/IOCTL_DISK_GET_DRIVE_GEOMETRY, storage.ioctl_disk_get_drive_geometry
f1_keywords:
 - "ntdddisk/IOCTL_DISK_GET_DRIVE_GEOMETRY"
 - "IOCTL_DISK_GET_DRIVE_GEOMETRY"
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
- IOCTL_DISK_GET_DRIVE_GEOMETRY
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_GET_DRIVE_GEOMETRY IOCTL


## -description



Returns information about the physical disk's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length

None


### -output-buffer

The driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry">DISK_GEOMETRY</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(DISK_GEOMETRY).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_UNRECOGNIZED_MEDIA, STATUS_INVALID_PARAMETER, STATUS_INVALID_DEVICE_REQUEST, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry">DISK_GEOMETRY</a>
 

 

