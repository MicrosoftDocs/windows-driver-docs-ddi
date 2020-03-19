---
UID: NI:ntdddisk.IOCTL_DISK_FORMAT_TRACKS
title: IOCTL_DISK_FORMAT_TRACKS (ntdddisk.h)
description: Formats the specified set of contiguous tracks on the disk.
old-location: storage\ioctl_disk_format_tracks.htm
tech.root: storage
ms.assetid: f27f962f-badc-4e6f-ad3b-ce2a0c8ce825
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_FORMAT_TRACKS IOCTL"]
ms.keywords: IOCTL_DISK_FORMAT_TRACKS, IOCTL_DISK_FORMAT_TRACKS control, IOCTL_DISK_FORMAT_TRACKS control code [Storage Devices], k307_c50ddad4-851d-474e-92c1-13520556173b.xml, ntdddisk/IOCTL_DISK_FORMAT_TRACKS, storage.ioctl_disk_format_tracks
f1_keywords:
 - "ntdddisk/IOCTL_DISK_FORMAT_TRACKS"
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
- IOCTL_DISK_FORMAT_TRACKS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_FORMAT_TRACKS IOCTL


## -description



Formats the specified set of contiguous tracks on the disk.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_format_parameters">FORMAT_PARAMETERS</a> data. <b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.


### -output-buffer

The device driver returns an array of BAD_TRACK_NUMBER values to the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

Length of the buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the size of the returned bad-track array when the <b>Status</b> field is set to STATUS_SUCCESS. Otherwise, the <b>Information</b> field is zero and the <b>Status</b> field possibly can be set to STATUS_INVALID_PARAMETER or STATUS_MEDIA_WRITE_PROTECTED if the media is removable.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_format_parameters">FORMAT_PARAMETERS</a>
 

 

