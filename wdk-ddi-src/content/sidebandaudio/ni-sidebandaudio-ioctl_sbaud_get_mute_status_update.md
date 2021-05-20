---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE
title: IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE (sidebandaudio.h)
description: 
ms.date: 10/05/2018
keywords: ["IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE IOCTL"]
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
 - IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE
 - sidebandaudio/IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE
---

# IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

The IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE IOCTL Gets the mute level setting of the Sideband Audio endpoint.

## -ioctlparameters

### -input-buffer

[SIDEBANDAUDIO_MUTE_PARAMS](./ns-sidebandaudio-_sidebandaudio_mute_params.md) with the 0 based endpoint index and channel number along with 'immediate' parameter indicating whether to process this IOCTL immediately or pend it for future updates.

### -input-buffer-length 

Size of [SIDEBANDAUDIO_MUTE_PARAMS](./ns-sidebandaudio-_sidebandaudio_mute_params.md).

### -output-buffer

[SIDEBANDAUDIO_MUTE_PARAMS](./ns-sidebandaudio-_sidebandaudio_mute_params.md)

### -output-buffer-length 

Size of [SIDEBANDAUDIO_MUTE_PARAMS](./ns-sidebandaudio-_sidebandaudio_mute_params.md).

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The mute update IOCTL can be used in two modes - update and immediate. If _**Immediate**_ parameter is set to TRUE, the IOCTL returns immediately with the current mute value for the requested channel. If the Immediate parameter is set to FALSE, the IRP is pended by the Sideband Audio Driver until there is a change in the device mute state. Audio driver should setup a pending mute IOCTL to get notified of any changes in hardware mute state.

## -see-also

[SIDEBANDAUDIO_MUTE_PARAMS](./ns-sidebandaudio-_sidebandaudio_mute_params.md)
