---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR
title: IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR (sidebandaudio.h)
description: 
ms.assetid: 3cbc7c1d-7540-44a7-bb02-85f0556c308d
ms.date: 10/05/2018
ms.topic: ioctl
f1_keywords:
 - "sidebandaudio/IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR"
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
- IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

The audio driver issues the IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR control code to get information about an enabled Sideband Audio device interface.
Specifically this returns the number of Audio endpoints available on a device that supports Sideband.




## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length 

None.

### -output-buffer

A buffer containing a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sidebandaudio/ns-sidebandaudio-_sidebandaudio_device_descriptor">SIDEBANDAUDIO_DEVICE_DESCRIPTOR</a> structure.

### -output-buffer-length 

The size of a <b>SIDEBANDAUDIO_DEVICE_DESCRIPTOR</b> structure.

### -in-out-buffer

<text></text>

### -inout-buffer-length 

<text></text>

### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the number of bytes that the routine writes to the output buffer.

<div> </div>
If Status is set to STATUS_BUFFER_TOO_SMALL, then the audio driver should read the <i>Information</i> member to get the size of the buffer that the caller should allocate for this request.

## -remarks


The audio driver sends this request to obtain information about an enabled Audio sideband device interface. The information does not change while the interface is enabled, but can change while the interface is disabled. Therefore the audio driver sends this request shortly after discovering an enabled device interface and uses the information to determine how many Sideband Audio endpoints are available.

The audio driver sends this request once with an output buffer size of zero (0) in order to determine the required output buffer size. In this case, the request will complete with Status STATUS_BUFFER_TOO_SMALL and set the <i>Information</i> member to the required buffer size. The audio driver then allocates the necessary storage space and sends the request again. Typically an audio driver will store a pointer to this storage location in its device context for reference during later activity.

The audio driver can then iteratively determine each endpoints capability with the IOCTL <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_get_endpoint_descriptor">IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR</a>.


## -see-also
