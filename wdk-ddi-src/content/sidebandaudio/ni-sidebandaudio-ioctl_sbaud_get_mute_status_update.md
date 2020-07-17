---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE
title: IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE (sidebandaudio.h)
description: 
ms.assetid: 0f733ef6-7993-4514-9d2c-f2e49c8d70dd
ms.date: 10/05/2018
keywords: ["IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE IOCTL"]
f1_keywords:
 - "sidebandaudio/IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE"
 - "IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- sidebandaudio.h
api_name: 
- IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

The IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE IOCTL Gets the mute level setting of the Sideband Audio endpoint.

## -ioctlparameters

### -input-buffer

[SIDEBANDAUDIO_MUTE_PARAMS](https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_mute_params) with the 0 based endpoint index and channel number along with 'immediate' parameter indicating whether to process this IOCTL immediately or pend it for future updates.

### -input-buffer-length 

Size of [SIDEBANDAUDIO_MUTE_PARAMS](https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_mute_params).

### -output-buffer

[SIDEBANDAUDIO_MUTE_PARAMS](https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_mute_params)

### -output-buffer-length 

Size of [SIDEBANDAUDIO_MUTE_PARAMS](https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_mute_params).

### -in-out-buffer

<text></text>

### -inout-buffer-length 

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks
The mute update IOCTL can be used in two modes - update and immediate. If SIDEBANDAUDIO_MUTE_PARAMS::Immediate parameter is set to TRUE, the IOCTL returns immediately with the current mute value for the requested channel. If the Immediate parameter is set to FALSE, the IRP is pended by the Sideband Audio Driver (like USB Audio) until there is a change in the device mute state. Audio driver should setup a pending mute IOCTL to get notified of any changes in hardware mute state.

## -see-also
[SIDEBANDAUDIO_MUTE_PARAMS](https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_mute_params)
