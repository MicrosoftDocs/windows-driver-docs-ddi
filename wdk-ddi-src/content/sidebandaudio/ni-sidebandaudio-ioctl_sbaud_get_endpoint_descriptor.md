---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR
title: IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR (sidebandaudio.h)
description: 
ms.assetid: 425f4c56-06d0-438a-81ec-f1335b52e398
ms.date: 10/05/2018
keywords: ["IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR IOCTL"]
f1_keywords:
 - "sidebandaudio/IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR"
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
- IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description
The audio driver issues the <b>IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR</b> control code to get information about an Audio endpoint exposed through Sideband Audio device interface.



## -ioctlparameters

### -input-buffer

A 0 based index value based on the number of Audio endpoints as reported by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_get_device_descriptor">IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR</a>.
This is a ULONG value from 0 to (N-1) where N is the number of Endpoints for the device.

### -input-buffer-length 

Size of ULONG.

### -output-buffer

A buffer containing a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_endpoint_descriptor">SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR</a> structure followed by any other data referenced by the structure. This is returned, if the output buffer size is sufficient and the request succeeds. In particular, the buffer includes storage for the string referenced by the <i>FriendlyName</i> field of the <b>SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR</b> structure.

### -output-buffer-length 

The size of a <b>SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR</b> structure and referenced data.

### -in-out-buffer

<text></text>

### -inout-buffer-length 

<text></text>

### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the number of bytes that the routine writes to the output buffer.

<div class="alert"><b>Note</b>  This can be larger than the size of the <b>SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR</b> structure, as the output buffer may contain other data referenced by the structure</div>
<div> </div>
If Status is set to STATUS_BUFFER_TOO_SMALL, then the audio driver should read the <i>Information</i> member to get the size of the buffer that the caller should allocate for this request.

## -remarks

The audio driver sends this request to obtain information about an enabled Audio Sideband Endpoint. The information does not change while the interface is enabled, but can change while the interface is disabled. Therefore the audio driver sends this request shortly after discovering an enabled device interface and uses the information to build an appropriate KSFILTER_DESCRIPTOR structure.

The audio driver sends this request once with an output buffer size of zero (0) in order to determine the required output buffer size. In this case, the request will complete with Status STATUS_BUFFER_TOO_SMALL and set the <i>Information</i> member to the required buffer size. The audio driver then allocates the necessary storage space and sends the request again. Typically an audio driver will store a pointer to this storage location in its device context for reference during later activity.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sidebandaudio/ns-sidebandaudio-_sidebandaudio_endpoint_descriptor">SIDEBANDAUDIO_ENDPOINT_DESCRIPTOR</a>
