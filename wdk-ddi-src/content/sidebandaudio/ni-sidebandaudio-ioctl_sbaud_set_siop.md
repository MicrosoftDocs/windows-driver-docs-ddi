---
UID: NI:sidebandaudio.IOCTL_SBAUD_SET_SIOP
title: IOCTL_SBAUD_SET_SIOP (sidebandaudio.h)
description: "The IOCTL_SBAUD_SET_SIOP IOCTL is used to set a SIOP command."
ms.date: 07/21/2023
keywords: ["IOCTL_SBAUD_SET_SIOP IOCTL"]
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
 - IOCTL_SBAUD_SET_SIOP
 - sidebandaudio/IOCTL_SBAUD_SET_SIOP
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_SET_SIOP
---

# IOCTL_SBAUD_SET_SIOP IOCTL

## -description

The IOCTL_SBAUD_SET_SIOP IOCTL is used to set a SIOP command. This control code is used by an audio driver when cooperating with the audio class drivers to operate a sideband connection.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

A [SIDEBANDAUDIO_SIOP_REQUEST_PARAM](ns-sidebandaudio-sidebandaudio_siop_request_param.md) union.

### -input-buffer-length

The length of the SIDEBANDAUDIO_SIOP_REQUEST_PARAM union.

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a NTSTATUS code.  For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

This IOCTL can only be called from kernel mode.

### Bluetooth A2DP

The A2DP driver saves the SIOP values in a collection of stream configuration vendor SIOPs and sends these SIOPs to the Bluetooth controller using HCI_VS_MSFT_Avdtp_Stream_Open while handling IOCTL_SBAUD_STREAM_OPEN. Any audio interface parameters returned by the Bluetooth controller are also stored in the collection of stream configuration vendor SIOPs. The audio driver can get these values at any time after the IOCTL completes.

The A2DP driver clears the collection of stream configuration vendor SIOPs when handling IOCTL_SBAUD_STREAM_CLOSE. (It does not clear the collection of system configuration vendor SIOPs.)

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[Introduction to I/O Control Codes](/windows-hardware/drivers/kernel/introduction-to-i-o-control-codes)

[sidebandaudio.h](index.md)
