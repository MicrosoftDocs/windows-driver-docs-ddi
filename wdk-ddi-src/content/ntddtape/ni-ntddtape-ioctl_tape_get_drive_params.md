---
UID: NI:ntddtape.IOCTL_TAPE_GET_DRIVE_PARAMS
title: IOCTL_TAPE_GET_DRIVE_PARAMS (ntddtape.h)
description: Returns information about the tape drive's capabilities, such as its default block size, maximum and minimum block sizes, maximum partition count, whether the drive has EEC, compression, data padding, and report-setmark capabilities, that is, which configurable features the drive supports, including the EOT warning zone size.
old-location: storage\ioctl_tape_get_drive_params.htm
tech.root: storage
ms.assetid: 05e45364-3544-477e-a06d-3aae93518b00
ms.date: 03/29/2018
keywords: ["IOCTL_TAPE_GET_DRIVE_PARAMS IOCTL"]
ms.keywords: IOCTL_TAPE_GET_DRIVE_PARAMS, IOCTL_TAPE_GET_DRIVE_PARAMS control, IOCTL_TAPE_GET_DRIVE_PARAMS control code [Storage Devices], k307_c6390200-5ccf-4a13-9b96-9f5aa5adee32.xml, ntddtape/IOCTL_TAPE_GET_DRIVE_PARAMS, storage.ioctl_tape_get_drive_params
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
 - IOCTL_TAPE_GET_DRIVE_PARAMS
 - ntddtape/IOCTL_TAPE_GET_DRIVE_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddtape.h
api_name:
 - IOCTL_TAPE_GET_DRIVE_PARAMS
---

# IOCTL_TAPE_GET_DRIVE_PARAMS IOCTL


## -description

Returns information about the tape drive's capabilities, such as its default block size, maximum and minimum block sizes, maximum partition count, whether the drive has EEC, compression, data padding, and report-setmark capabilities, that is, which configurable features the drive supports, including the EOT warning zone size.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The driver returns the <a href="/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_get_drive_parameters">TAPE_GET_DRIVE_PARAMETERS</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(TAPE_GET_DRIVE_PARAMETERS).

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, or STATUS_DEVICE_NOT_READY.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_get_drive_parameters">TAPE_GET_DRIVE_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>



<a href="/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetDriveParameters</a>