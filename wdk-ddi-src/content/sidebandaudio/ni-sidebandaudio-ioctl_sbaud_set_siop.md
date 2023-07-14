---
UID: NI:sidebandaudio.IOCTL_SBAUD_SET_SIOP
title: IOCTL_SBAUD_SET_SIOP (sidebandaudio.h)
description: "Learn more about: IOCTL_SBAUD_SET_SIOP IOCTL"
ms.date: 10/05/2018
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

This control code is used by an audio driver when cooperating with the audio class drivers to operate a sideband connection.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a NTSTATUS code.  For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).


## -remarks

This is one of the IOCTLs used for KS pin state transitions. The audio driver sends these requests on certain KS pin state transitions.


## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[Introduction to I/O Control Codes](/windows-hardware/drivers/kernel/introduction-to-i-o-control-codes)

[sidebandaudio.h](index.md)
