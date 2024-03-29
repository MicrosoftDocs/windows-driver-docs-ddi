---
UID: NI:ntdddisk.IOCTL_DISK_VERIFY
title: IOCTL_DISK_VERIFY (ntdddisk.h)
description: Performs verification for a specified extent on a disk.
old-location: storage\ioctl_disk_verify.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_VERIFY IOCTL"]
ms.keywords: IOCTL_DISK_VERIFY, IOCTL_DISK_VERIFY control, IOCTL_DISK_VERIFY control code [Storage Devices], k307_bafd5046-34ca-4e76-b1a6-bf5195adbb3b.xml, ntdddisk/IOCTL_DISK_VERIFY, storage.ioctl_disk_verify
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
 - IOCTL_DISK_VERIFY
 - ntdddisk/IOCTL_DISK_VERIFY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntdddisk.h
api_name:
 - IOCTL_DISK_VERIFY
---

# IOCTL_DISK_VERIFY IOCTL


## -description

Performs verification for a specified extent on a disk.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_verify_information">VERIFY_INFORMATION</a> data specifying the starting offset and length to be verified.

### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(VERIFY_INFORMATION).

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero to prevent the I/O manager from copying data from <b>SystemBuffer</b> back into the user area. 

If the request is successful, then the <b>Status</b> field is set to STATUS_SUCCESS. Otherwise, the <b>Status</b> field can be set to STATUS_BUFFER_TOO_SMALL, STATUS_INFO_LENGTH_MISMATCH, STATUS_INVALID_PARAMETER, STATUS_INSUFFICIENT_RESOURCES, STATUS_NONEXISTENT_SECTOR, STATUS_DEVICE_DATA_ERROR, STATUS_INVALID_DEVICE_REQUEST, STATUS_IO_TIMEOUT, or STATUS_DEVICE_NOT_CONNECTED.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_verify_information">VERIFY_INFORMATION</a>
