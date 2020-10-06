---
UID: NI:ntdddisk.IOCTL_DISK_GET_DRIVE_LAYOUT_EX
title: IOCTL_DISK_GET_DRIVE_LAYOUT_EX (ntdddisk.h)
description: Returns information about the number of partitions, disk signature, and features of each partition on a disk. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_get_drive_layout_ex.htm
tech.root: storage
ms.assetid: b0ffd1a6-aaa1-4001-a02b-6c0693b7ec5c
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_GET_DRIVE_LAYOUT_EX IOCTL"]
ms.keywords: IOCTL_DISK_GET_DRIVE_LAYOUT_EX, IOCTL_DISK_GET_DRIVE_LAYOUT_EX control, IOCTL_DISK_GET_DRIVE_LAYOUT_EX control code [Storage Devices], k307_81993d9b-900f-412c-ac07-f0765114141f.xml, ntdddisk/IOCTL_DISK_GET_DRIVE_LAYOUT_EX, storage.ioctl_disk_get_drive_layout_ex
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
 - IOCTL_DISK_GET_DRIVE_LAYOUT_EX
 - ntdddisk/IOCTL_DISK_GET_DRIVE_LAYOUT_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntdddisk.h
api_name:
 - IOCTL_DISK_GET_DRIVE_LAYOUT_EX
---

# IOCTL_DISK_GET_DRIVE_LAYOUT_EX IOCTL


## -description

Returns information about the number of partitions, disk signature, and features of each partition on a disk. (Floppy drivers need not handle this request.)

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The driver returns the <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_drive_layout_information_ex">DRIVE_LAYOUT_INFORMATION_EX</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(DRIVE_LAYOUT_INFORMATION_EX). Note that this structure contains a variable-sized array of <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information_ex">PARTITION_INFORMATION_EX</a> elements.

To determine the size of output buffer that is required, caller should send this IOCTL request in a loop. Every time the storage stack rejects the IOCTL with an error message indicating that the buffer was too small, caller should double the buffer size.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_drive_layout_information">DRIVE_LAYOUT_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information">PARTITION_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information_ex">PARTITION_INFORMATION_EX</a>