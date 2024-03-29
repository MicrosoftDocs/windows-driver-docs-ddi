---
UID: NI:ntdddisk.IOCTL_DISK_GET_CACHE_INFORMATION
title: IOCTL_DISK_GET_CACHE_INFORMATION (ntdddisk.h)
description: Returns disk cache configuration data.
old-location: storage\ioctl_disk_get_cache_information.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_GET_CACHE_INFORMATION IOCTL"]
ms.keywords: IOCTL_DISK_GET_CACHE_INFORMATION, IOCTL_DISK_GET_CACHE_INFORMATION control, IOCTL_DISK_GET_CACHE_INFORMATION control code [Storage Devices], k307_1471eb7a-169f-4653-9bfe-01714d6299b7.xml, ntdddisk/IOCTL_DISK_GET_CACHE_INFORMATION, storage.ioctl_disk_get_cache_information
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
 - IOCTL_DISK_GET_CACHE_INFORMATION
 - ntdddisk/IOCTL_DISK_GET_CACHE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntdddisk.h
api_name:
 - IOCTL_DISK_GET_CACHE_INFORMATION
---

# IOCTL_DISK_GET_CACHE_INFORMATION IOCTL


## -description

Returns disk cache configuration data.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The device driver returns the <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_cache_information">DISK_CACHE_INFORMATION</a> in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be >= <b>sizeof</b>(DISK_CACHE_INFORMATION). Otherwise, the driver returns with an error status of STATUS_BUFFER_TOO_SMALL.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the size of the block of status information being returned, <b>sizeof</b>(DISK_CACHE_INFORMATION). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_DEVICE_NOT_READY, STATUS_BUFFER_TOO_SMALL, STATUS_INSUFFICIENT_RESOURCES, STATUS_IO_DEVICE_ERROR, or STATUS_NOT_SUPPORTED.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_cache_information">DISK_CACHE_INFORMATION</a>
