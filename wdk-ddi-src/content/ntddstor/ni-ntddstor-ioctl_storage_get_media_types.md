---
UID: NI:ntddstor.IOCTL_STORAGE_GET_MEDIA_TYPES
title: IOCTL_STORAGE_GET_MEDIA_TYPES (ntddstor.h)
description: Returns information about the geometry of floppy drives.
old-location: storage\ioctl_storage_get_media_types.htm
tech.root: storage
ms.assetid: 213711fb-26eb-443b-aff4-8f84b643adb3
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_GET_MEDIA_TYPES IOCTL"]
ms.keywords: IOCTL_STORAGE_GET_MEDIA_TYPES, IOCTL_STORAGE_GET_MEDIA_TYPES control, IOCTL_STORAGE_GET_MEDIA_TYPES control code [Storage Devices], k307_9e0698c0-04ff-48b5-ba02-903c59bf6f58.xml, ntddstor/IOCTL_STORAGE_GET_MEDIA_TYPES, storage.ioctl_storage_get_media_types
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_GET_MEDIA_TYPES"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
- Ntddstor.h
api_name:
- IOCTL_STORAGE_GET_MEDIA_TYPES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_GET_MEDIA_TYPES IOCTL


## -description



Returns information about the geometry of floppy drives.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry">DISK_GEOMETRY</a> records for the types of media it supports in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least (<i>NumberOfSupportedMediaTypes</i> * <b>sizeof</b>(DISK_GEOMETRY)).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_BUFFER_TOO_SMALL, or STATUS_BUFFER_OVERFLOW.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry">DISK_GEOMETRY</a>
 

 

