---
UID: NI:ntddstor.IOCTL_STORAGE_MANAGE_BYPASS_IO
tech.root: storage
title: IOCTL_STORAGE_MANAGE_BYPASS_IO
ms.date: 07/08/2021
targetos: Windows
description: The IOCTL_STORAGE_MANAGE_BYPASS_IO control code controls BypassIO operations on a given file in all layers of the volume and storage stacks.
prerelease: false
req.construct-type: ioctl
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - IOCTL_STORAGE_MANAGE_BYPASS_IO
f1_keywords:
 - IOCTL_STORAGE_MANAGE_BYPASS_IO
 - ntddstor/IOCTL_STORAGE_MANAGE_BYPASS_IO
dev_langs:
 - c++
---

## -description

The **IOCTL_STORAGE_MANAGE_BYPASS_IO** control code controls BypassIO operations on a given file in all layers of the volume and storage stacks.

## -ioctlparameters

### -input-buffer

The buffer at **Irp->AssociatedIrp.SystemBuffer** contains a [**BPIO_INPUT**](ns-ntddstor-bpio_input.md) structure with information related to a BypassIO request.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least ```sizeof(BPIO_INPUT)```.

### -output-buffer

The driver returns information in a [**BPIO_OUTPUT**](ns-ntddstor-bpio_output.md) structure in the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location of the IRP indicates the size of the output buffer, in bytes. **OutputBufferLength** must be at least ```sizeof(BPIO_OUTPUT)```.

### -status-block

The **Status** field can be set to STATUS_SUCCESS, or an error status such as STATUS_INVALID_PARAMETER, STATUS_INFO_LENGTH_MISMATCH, STATUS_BUFFER_TOO_SMALL, or STATUS_NOT_SUPPORTED.

## -remarks

Only file systems send **IOCTL_STORAGE_MANAGE_BYPASS_IO**. A file system sends this IOCTL as appropriate in response to a [**FSCTL_MANAGE_BYPASS_IO**](../ntifs/ni-ntifs-fsctl_manage_bypass_io.md) control code.

See [BypassIO for storage drivers](/windows-hardware/drivers/storage/bypassio) for more information.

## -see-also

[**BPIO_INPUT**](ns-ntddstor-bpio_input.md)

[**BPIO_OUTPUT**](ns-ntddstor-bpio_output.md)

[**FSCTL_MANAGE_BYPASS_IO**](../ntifs/ni-ntifs-fsctl_manage_bypass_io.md)
