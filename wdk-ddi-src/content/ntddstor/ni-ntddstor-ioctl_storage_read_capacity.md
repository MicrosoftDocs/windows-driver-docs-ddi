---
UID: NI:ntddstor.IOCTL_STORAGE_READ_CAPACITY
title: IOCTL_STORAGE_READ_CAPACITY (ntddstor.h)
description: The IOCTL_STORAGE_READ_CAPACITY request returns the read capacity information for the target storage device.
old-location: storage\ioctl_storage_read_capacity.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_READ_CAPACITY IOCTL"]
ms.keywords: IOCTL_STORAGE_READ_CAPACITY, IOCTL_STORAGE_READ_CAPACITY control, IOCTL_STORAGE_READ_CAPACITY control code [Storage Devices], ntddstor/IOCTL_STORAGE_READ_CAPACITY, storage.ioctl_storage_read_capacity
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
 - IOCTL_STORAGE_READ_CAPACITY
 - ntddstor/IOCTL_STORAGE_READ_CAPACITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - IOCTL_STORAGE_READ_CAPACITY
---

# IOCTL_STORAGE_READ_CAPACITY IOCTL


## -description

The <b>IOCTL_STORAGE_READ_CAPACITY</b> request returns the read capacity information for the target storage device.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The buffer at <i>Irp->AssociatedIrp.SystemBuffer</i> contains a <a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_read_capacity">STORAGE_READ_CAPACITY</a> structure.

### -output-buffer-length

<i>Parameters.DeviceIoControl.OutputBufferLength</i> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(STORAGE_READ_CAPACITY).

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_BUFFER_TOO_SMALL, STATUS_BUFFER_OVERFLOW, or some other error status.

## -remarks

A <b>IOCTL_STORAGE_READ_CAPACITY</b> request returns the disk capacity information retrieved during disk initialization. The capacity information is obtained by the system with the SCSI READ CAPACITY command.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_read_capacity">STORAGE_READ_CAPACITY</a>
