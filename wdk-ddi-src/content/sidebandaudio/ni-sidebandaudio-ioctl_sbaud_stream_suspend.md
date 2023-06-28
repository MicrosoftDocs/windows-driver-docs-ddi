---
UID: NI:sidebandaudio.IOCTL_SBAUD_STREAM_SUSPEND
title: IOCTL_SBAUD_STREAM_SUSPEND (sidebandaudio.h)
description: "On transition below KSSTATE_RUN, send IOCTL_SBAUD_STREAM_SUSPEND."
ms.date: 06/28/2023
keywords: ["IOCTL_SBAUD_STREAM_SUSPEND IOCTL"]
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
 - IOCTL_SBAUD_STREAM_SUSPEND
 - sidebandaudio/IOCTL_SBAUD_STREAM_SUSPEND
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_STREAM_SUSPEND
---

# IOCTL_SBAUD_STREAM_SUSPEND IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

This control codes used by an audio driver when cooperating with the Audio class drivers to operate a Sideband connection. On transition below KSSTATE_RUN, send **IOCTL_SBAUD_STREAM_SUSPEND**.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

(Additional Information Pending)

### -input-buffer-length

Size of ULONG.

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a NTSTATUS code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

This one of the IOCTLs used for KS pin state transitions. The audio driver sends these requests on certain KS pin state transitions.

- On first transition above KSSTATE_STOP (normally to KSSTATE_ACQUIRE), send [IOCTL_SBAUD_STREAM_OPEN](/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_stream_open).
- On transition up to KSSTATE_RUN, send [IOCTL_SBAUD_STREAM_START](/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_stream_start).
- On transition below KSSTATE_RUN, send [IOCTL_SBAUD_STREAM_SUSPEND](/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_stream_suspend).
- On closure of KS pin, send [IOCTL_SBAUD_STREAM_CLOSE](/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_stream_close).

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[sidebandaudio.h](index.md)
