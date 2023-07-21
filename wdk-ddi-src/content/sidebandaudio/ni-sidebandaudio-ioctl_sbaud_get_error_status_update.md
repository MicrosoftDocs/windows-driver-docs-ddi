---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_ERROR_STATUS_UPDATE
title: IOCTL_SBAUD_GET_ERROR_STATUS_UPDATE (sidebandaudio.h)
description: "The IOCTL_SBAUD_GET_ERROR_STATUS_UPDATE  IOCTL is used for error status updates."
ms.date: 07/14/2023
keywords: ["IOCTL_SBAUD_GET_ERROR_STATUS_UPDATE IOCTL"]
req.header: sidebandaudio.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - IOCTL_SBAUD_GET_ERROR_STATUS_UPDATE
 - sidebandaudio/IOCTL_SBAUD_GET_ERROR_STATUS_UPDATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_GET_ERROR_STATUS_UPDATE
---

# IOCTL_SBAUD_GET_ERROR_STATUS_UPDATE IOCTL

## -description

The **IOCTL_SBAUD_GET_ERROR_STATUS_UPDATE** is used for error status updates.  This control code is used by an audio driver when cooperating with the audio class drivers to operate a sideband connection.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

A [SIDEBANDAUDIO_DEVICE_ERROR](ns-sidebandaudio-_sidebandaudio_device_error.md) structure with the 0 based endpoint index and channel number along with 'immediate' parameter indicating whether to process this IOCTL immediately or pend it for future updates.

### -input-buffer-length

The size of the SIDEBANDAUDIO_DEVICE_ERROR structure.

### -output-buffer

A [SIDEBANDAUDIO_DEVICE_ERROR structure](ns-sidebandaudio-_sidebandaudio_device_error.md) that describes the device error status.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a NTSTATUS code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

This IOCTL can only be called from kernel mode.

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[Introduction to I/O Control Codes](/windows-hardware/drivers/kernel/introduction-to-i-o-control-codes)

[sidebandaudio.h](index.md)
