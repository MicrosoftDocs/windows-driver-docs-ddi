---
UID: NI:sidebandaudio.IOCTL_SBAUD_SET_MUTE
title: IOCTL_SBAUD_SET_MUTE (sidebandaudio.h)
description: "The IOCTL_SBAUD_SET_MUTE IOCTL is used to set the render (speaker) mute."
ms.date: 10/05/2018
keywords: ["IOCTL_SBAUD_SET_MUTE IOCTL"]
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
 - IOCTL_SBAUD_SET_MUTE
 - sidebandaudio/IOCTL_SBAUD_SET_MUTE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_SET_MUTE
---

# IOCTL_SBAUD_SET_MUTE IOCTL

## -description

The **IOCTL_SBAUD_SET_MUTE IOCTL** is used to set the render (speaker) mute. This control code is used by an audio driver when cooperating with the audio class drivers to operate a sideband connection.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

[SIDEBANDAUDIO_MUTE_PARAMS](./ns-sidebandaudio-_sidebandaudio_mute_params.md) with the 0 based endpoint index and channel number along with 'immediate' parameter indicating whether to process this IOCTL immediately or pend it for future updates.

### -input-buffer-length

Size of [SIDEBANDAUDIO_MUTE_PARAMS](./ns-sidebandaudio-_sidebandaudio_mute_params.md).

### -output-buffer

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
