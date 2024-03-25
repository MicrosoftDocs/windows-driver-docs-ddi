---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_CONNECTION_STATUS_UPDATE
title: IOCTL_SBAUD_GET_CONNECTION_STATUS_UPDATE (sidebandaudio.h)
description: "The IOCTL_SBAUD_GET_CONNECTION_STATUS_UPDATE IOCTL control code code gets a connection status update."
ms.date: 07/20/2023
keywords: ["IOCTL_SBAUD_GET_CONNECTION_STATUS_UPDATE IOCTL"]
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
 - IOCTL_SBAUD_GET_CONNECTION_STATUS_UPDATE
 - sidebandaudio/IOCTL_SBAUD_GET_CONNECTION_STATUS_UPDATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_GET_CONNECTION_STATUS_UPDATE
---

# IOCTL_SBAUD_GET_CONNECTION_STATUS_UPDATE IOCTL

## -description

The **IOCTL_SBAUD_GET_CONNECTION_STATUS_UPDATE** IOCTL control code gets a connection status update. It is used by an audio driver when cooperating with the Audio class drivers to operate a Sideband connection.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

A [SIDEBANDAUDIO_CONNECTION_PARAMS](ns-sidebandaudio-_sidebandaudio_connection_params.md) structure.

### -input-buffer-length

The size of the SIDEBANDAUDIO_CONNECTION_PARAMS structure.

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

[sidebandaudio.h](index.md)

[Introduction to I/O Control Codes](/windows-hardware/drivers/kernel/introduction-to-i-o-control-codes)
