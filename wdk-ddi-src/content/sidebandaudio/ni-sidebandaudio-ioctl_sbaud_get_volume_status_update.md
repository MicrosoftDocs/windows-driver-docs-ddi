---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_VOLUME_STATUS_UPDATE
title: IOCTL_SBAUD_GET_VOLUME_STATUS_UPDATE (sidebandaudio.h)
description: 
ms.assetid: e9255cb1-ba40-4432-bbe7-72a9d57d4b6d
ms.date: 10/05/2018
keywords: ["IOCTL_SBAUD_GET_VOLUME_STATUS_UPDATE IOCTL"]
f1_keywords:
 - "sidebandaudio/IOCTL_SBAUD_GET_VOLUME_STATUS_UPDATE"
 - "IOCTL_SBAUD_GET_VOLUME_STATUS_UPDATE"
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
- IOCTL_SBAUD_GET_VOLUME_STATUS_UPDATE
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# IOCTL_SBAUD_GET_VOLUME_STATUS_UPDATE IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

The IOCTL_SBAUD_GET_VOLUME_STATUS_UPDATE IOCTL Gets the volume level setting of the Sideband Audio endpoint.


## -ioctlparameters

### -input-buffer
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_volume_params">SIDEBANDAUDIO_VOLUME_PARAMS</a> with the 0 based endpoint index and channel number along with 'immediate' parameter indicating whether to process this IOCTL immediately or pend it for future updates.

### -input-buffer-length 

Szie of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_volume_params">SIDEBANDAUDIO_VOLUME_PARAMS</a>.

### -output-buffer

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_volume_params">SIDEBANDAUDIO_VOLUME_PARAMS</a>.

### -output-buffer-length 

Size of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_volume_params">SIDEBANDAUDIO_VOLUME_PARAMS</a>.

### -in-out-buffer

<text></text>

### -inout-buffer-length 

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks
The volume update IOCTL can be used in two modes - update and immediate. If SIDEBANDAUDIO_VOLUME_PARAMS::Immediate parameter is set to TRUE, the IOCTL returns immediately with the current volume value for the requested channel. If the Immediate parameter is set to FALSE, the IRP is pended by the Sideband Audio Driver (like USB Audio) until there is a change in the device volume. Audio driver should setup a pending volume IOCTL to get notified of any changes in hardware volume.

## -see-also
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_volume_params">SIDEBANDAUDIO_VOLUME_PARAMS</a>
