---
UID: NI:ntdddisk.IOCTL_DISK_SET_CACHE_INFORMATION
title: IOCTL_DISK_SET_CACHE_INFORMATION (ntdddisk.h)
description: Sets disk cache configuration data.
old-location: storage\ioctl_disk_set_cache_information.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_SET_CACHE_INFORMATION IOCTL"]
ms.keywords: IOCTL_DISK_SET_CACHE_INFORMATION, IOCTL_DISK_SET_CACHE_INFORMATION control, IOCTL_DISK_SET_CACHE_INFORMATION control code [Storage Devices], k307_4f1b855c-4788-48e9-bc26-7addf3c7e3a9.xml, ntdddisk/IOCTL_DISK_SET_CACHE_INFORMATION, storage.ioctl_disk_set_cache_information
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
 - IOCTL_DISK_SET_CACHE_INFORMATION
 - ntdddisk/IOCTL_DISK_SET_CACHE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntdddisk.h
api_name:
 - IOCTL_DISK_SET_CACHE_INFORMATION
---

# IOCTL_DISK_SET_CACHE_INFORMATION IOCTL


## -description

Sets disk cache configuration data.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The input buffer.

### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be >= <b>sizeof</b>(DISK_CACHE_INFORMATION). Otherwise, the driver returns with an error status of STATUS_INFO_LENGTH_MISMATCH.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS or STATUS_INFO_LENGTH_MISMATCH if the input buffer is not large enough.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_cache_information">DISK_CACHE_INFORMATION</a>
