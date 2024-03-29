---
UID: NI:ntdddisk.IOCTL_DISK_IS_WRITABLE
title: IOCTL_DISK_IS_WRITABLE (ntdddisk.h)
description: Determines whether a disk is writable.
old-location: storage\ioctl_disk_is_writable.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_IS_WRITABLE IOCTL"]
ms.keywords: IOCTL_DISK_IS_WRITABLE, IOCTL_DISK_IS_WRITABLE control, IOCTL_DISK_IS_WRITABLE control code [Storage Devices], k307_b5d259a8-bf23-4475-98ce-69c87b3de52c.xml, ntdddisk/IOCTL_DISK_IS_WRITABLE, storage.ioctl_disk_is_writable
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_DISK_IS_WRITABLE
 - ntdddisk/IOCTL_DISK_IS_WRITABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntdddisk.h
api_name:
 - IOCTL_DISK_IS_WRITABLE
---

# IOCTL_DISK_IS_WRITABLE IOCTL


## -description

Determines whether a disk is writable.

## -ioctlparameters

### -ioctl-major-code

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

The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES, STATUS_IO_DEVICE_ERROR, or STATUS_MEDIA_WRITE_PROTECTED.

