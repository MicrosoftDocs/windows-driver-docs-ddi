---
UID: NI:ntddtape.IOCTL_TAPE_SET_DRIVE_PARAMS
title: IOCTL_TAPE_SET_DRIVE_PARAMS (ntddtape.h)
description: Adjusts a tape drive's configurable parameters.
old-location: storage\ioctl_tape_set_drive_params.htm
tech.root: storage
ms.assetid: aa625cbf-fa0f-420a-b8ec-2babf4c4ec17
ms.date: 03/29/2018
keywords: ["IOCTL_TAPE_SET_DRIVE_PARAMS IOCTL"]
ms.keywords: IOCTL_TAPE_SET_DRIVE_PARAMS, IOCTL_TAPE_SET_DRIVE_PARAMS control, IOCTL_TAPE_SET_DRIVE_PARAMS control code [Storage Devices], k307_8467b086-c211-4e26-ac65-2d12ea1c4c73.xml, ntddtape/IOCTL_TAPE_SET_DRIVE_PARAMS, storage.ioctl_tape_set_drive_params
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
 - IOCTL_TAPE_SET_DRIVE_PARAMS
 - ntddtape/IOCTL_TAPE_SET_DRIVE_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddtape.h
api_name:
 - IOCTL_TAPE_SET_DRIVE_PARAMS
---

# IOCTL_TAPE_SET_DRIVE_PARAMS IOCTL


## -description

Adjusts a tape drive's configurable parameters. The miniclass driver can ignore parameters that its device does not support. The calling application is responsible for determining whether a device supports a particular feature before attempting to set it.

## -ioctlparameters

### -input-buffer

       The <a href="/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_set_drive_parameters">TAPE_SET_DRIVE_PARAMETERS</a> structure in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the values to be set.

### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(TAPE_SET_DRIVE_PARAMETERS).

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_INVALID_DEVICE_REQUEST, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_INFO_LENGTH_MISMATCH, or STATUS_DEVICE_NOT_READY.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_set_drive_parameters">TAPE_SET_DRIVE_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>



<a href="/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetDriveParameters</a>