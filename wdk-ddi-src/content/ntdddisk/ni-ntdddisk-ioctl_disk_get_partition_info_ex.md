---
UID: NI:ntdddisk.IOCTL_DISK_GET_PARTITION_INFO_EX
title: IOCTL_DISK_GET_PARTITION_INFO_EX (ntdddisk.h)
description: Returns information about the type, size, and nature of a disk partition. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_get_partition_info_ex.htm
tech.root: storage
ms.assetid: 561967a3-8b57-4f24-921a-a70e1a6c717a
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_GET_PARTITION_INFO_EX IOCTL"]
ms.keywords: IOCTL_DISK_GET_PARTITION_INFO_EX, IOCTL_DISK_GET_PARTITION_INFO_EX control, IOCTL_DISK_GET_PARTITION_INFO_EX control code [Storage Devices], k307_e9e632f5-6cc9-4494-876a-2e2f9071358b.xml, ntdddisk/IOCTL_DISK_GET_PARTITION_INFO_EX, storage.ioctl_disk_get_partition_info_ex
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
 - IOCTL_DISK_GET_PARTITION_INFO_EX
 - ntdddisk/IOCTL_DISK_GET_PARTITION_INFO_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntdddisk.h
api_name:
 - IOCTL_DISK_GET_PARTITION_INFO_EX
---

# IOCTL_DISK_GET_PARTITION_INFO_EX IOCTL


## -description

Returns information about the type, size, and nature of a disk partition. (Floppy drivers need not handle this request.)

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information_ex">PARTITION_INFORMATION_EX</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(PARTITION_INFORMATION_EX).

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_PARAMETER, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, or STATUS_BUFFER_TOO_SMALL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information">PARTITION_INFORMATION</a>

