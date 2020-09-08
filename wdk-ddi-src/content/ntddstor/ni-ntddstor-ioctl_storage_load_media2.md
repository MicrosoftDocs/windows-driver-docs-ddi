---
UID: NI:ntddstor.IOCTL_STORAGE_LOAD_MEDIA2
title: IOCTL_STORAGE_LOAD_MEDIA2 (ntddstor.h)
description: Causes media to be loaded in a device that the caller has opened with FILE_READ_ATTRIBUTES.
old-location: storage\ioctl_storage_load_media2.htm
tech.root: storage
ms.assetid: ba458d46-9b5f-4ee3-80fa-59277e97fb4a
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_LOAD_MEDIA2 IOCTL"]
ms.keywords: IOCTL_STORAGE_LOAD_MEDIA2, IOCTL_STORAGE_LOAD_MEDIA2 control, IOCTL_STORAGE_LOAD_MEDIA2 control code [Storage Devices], k307_3952f49a-8ca1-42eb-afd0-cb0e6eef66fc.xml, ntddstor/IOCTL_STORAGE_LOAD_MEDIA2, storage.ioctl_storage_load_media2
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_STORAGE_LOAD_MEDIA2
 - ntddstor/IOCTL_STORAGE_LOAD_MEDIA2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - IOCTL_STORAGE_LOAD_MEDIA2
---

# IOCTL_STORAGE_LOAD_MEDIA2 IOCTL


## -description

Causes media to be loaded in a device that the caller has opened with FILE_READ_ATTRIBUTES. Because no file system is mounted when a device is opened in this way, this request can be processed much more quickly than an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_load_media">IOCTL_STORAGE_LOAD_MEDIA</a> request.

Input, output, and I/O status block values for IOCTL_STORAGE_LOAD_MEDIA2 are identical to those for IOCTL_STORAGE_LOAD_MEDIA.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_NO_MEDIA_IN_DEVICE, STATUS_BUFFER_TOO_SMALL, or STATUS_DEVICE_NOT_CONNECTED.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_load_media">IOCTL_STORAGE_LOAD_MEDIA</a>

