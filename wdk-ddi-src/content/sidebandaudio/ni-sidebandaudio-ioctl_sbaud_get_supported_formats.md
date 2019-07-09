---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_SUPPORTED_FORMATS
title: IOCTL_SBAUD_GET_SUPPORTED_FORMATS (sidebandaudio.h)
description: 
ms.assetid: 0e17eae1-e498-43b6-88d8-6a5f0752f3f0
ms.date: 10/05/2018
ms.topic: ioctl
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
- IOCTL_SBAUD_GET_SUPPORTED_FORMATS
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# IOCTL_SBAUD_GET_SUPPORTED_FORMATS IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

The audio driver issues the <b>IOCTL_SBAUD_GET_SUPPORTED_FORMATS</b> control code to get information about the stream formats supported by Sideband Audio endpoint.

## -ioctlparameters

### -input-buffer

[SIDEBANDAUDIO_SUPPORTED_FORMATS](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sidebandaudio/ns-sidebandaudio-_sidebandaudio_supported_formats) containing endpoint index, and array of formats supported by the Audio driver.

### -input-buffer-length 

Size of [SIDEBANDAUDIO_SUPPORTED_FORMATS](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sidebandaudio/ns-sidebandaudio-_sidebandaudio_supported_formats) including storage for array of formats.

### -output-buffer

[SIDEBANDAUDIO_SUPPORTED_FORMATS](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sidebandaudio/ns-sidebandaudio-_sidebandaudio_supported_formats). The sideband driver will return intersection of the Sideband audio formats with the formats supplied dy Audio driver as input parameter.

### -output-buffer-length 

Size of [SIDEBANDAUDIO_SUPPORTED_FORMATS](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sidebandaudio/ns-sidebandaudio-_sidebandaudio_supported_formats) including storage for array of formats.

### -in-out-buffer

<text></text>

### -inout-buffer-length 

<text></text>

### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the number of bytes that the routine writes to the output buffer.

If Status is set to STATUS_BUFFER_TOO_SMALL, then the audio driver should read the <i>Information</i> member to get the size of the buffer that the caller should allocate for this request.

## -remarks

## -see-also
[SIDEBANDAUDIO_SUPPORTED_FORMATS](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sidebandaudio/ns-sidebandaudio-_sidebandaudio_supported_formats)
