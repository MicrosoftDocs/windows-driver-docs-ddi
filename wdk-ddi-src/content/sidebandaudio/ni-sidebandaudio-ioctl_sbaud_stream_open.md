---
UID: NI:sidebandaudio.IOCTL_SBAUD_STREAM_OPEN
title: IOCTL_SBAUD_STREAM_OPEN (sidebandaudio.h)
description: "On first transition above KSSTATE_STOP (normally to KSSTATE_ACQUIRE), send IOCTL_SBAUD_STREAM_OPEN."
ms.date: 06/28/2023
keywords: ["IOCTL_SBAUD_STREAM_OPEN IOCTL"]
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
 - IOCTL_SBAUD_STREAM_OPEN
 - sidebandaudio/IOCTL_SBAUD_STREAM_OPEN
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_STREAM_OPEN
---

# IOCTL_SBAUD_STREAM_OPEN IOCTL

## -description

This control code is used by an audio driver when cooperating with the audio class drivers to operate a sideband connection. On first transition above KSSTATE_STOP (normally to KSSTATE_ACQUIRE), send **IOCTL_SBAUD_STREAM_OPEN**.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

A [SIDEBANDAUDIO_STREAM_OPEN_PARAMS](./ns-sidebandaudio-sidebandaudio_stream_open_params.md) structure. It contains a 0 based index value based on the number of Audio endpoints as reported by the [IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR](./ni-sidebandaudio-ioctl_sbaud_get_device_descriptor.md). This is a ULONG value from 0 to (N-1) where N is the number of Endpoints for the device.

### -input-buffer-length

Size of ULONG. This is the size of the [SIDEBANDAUDIO_STREAM_OPEN_PARAMS](./ns-sidebandaudio-sidebandaudio_stream_open_params.md)

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a NTSTATUS code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

This is one of the IOCTLs used for KS pin state transitions. The audio driver sends these requests on certain KS pin state transitions.

- On first transition above KSSTATE_STOP (normally to KSSTATE_ACQUIRE), send [IOCTL_SBAUD_STREAM_OPEN](/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_stream_open).
- On transition up to KSSTATE_RUN, send [IOCTL_SBAUD_STREAM_START](/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_stream_start).
- On transition below KSSTATE_RUN, send [IOCTL_SBAUD_STREAM_SUSPEND](/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_stream_suspend).
- On closure of KS pin, send [IOCTL_SBAUD_STREAM_CLOSE](/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_stream_close).

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[Introduction to I/O Control Codes](/windows-hardware/drivers/kernel/introduction-to-i-o-control-codes)

[sidebandaudio.h](index.md)