---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR
title: IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR (sidebandaudio.h)
description: "The audio driver issues the IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR to get information about an enabled sideband audio device interface."
ms.date: 06/27/2023
keywords: ["IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR IOCTL"]
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
 - IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR
 - sidebandaudio/IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR
---

# IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR

## -description

The audio driver issues the **IOCTL_SBAUD_GET_DEVICE_DESCRIPTOR** to get information about an enabled sideband audio device interface. Specifically this returns the number of Audio endpoints available on a device that supports Sideband. This information is returned in a  [Audio device descriptor](./ns-sidebandaudio-_sidebandaudio_device_descriptor.md) structure.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

NULL.

### -input-buffer-length

0.

### -output-buffer

A buffer containing a [SIDEBANDAUDIO_DEVICE_DESCRIPTOR](./ns-sidebandaudio-_sidebandaudio_device_descriptor.md) structure.

### -output-buffer-length

The size of a <b>SIDEBANDAUDIO_DEVICE_DESCRIPTOR</b> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the number of bytes that the routine writes to the output buffer.

If Status is set to STATUS_BUFFER_TOO_SMALL, then the audio driver should read the <i>Information</i> member to get the size of the buffer that the caller should allocate for this request.

## -remarks

The audio driver sends this request to obtain information about an enabled Audio sideband device interface. The information does not change while the interface is enabled, but can change while the interface is disabled. The audio driver sends this request shortly after discovering an enabled sideband audio device interface and uses the information to determine how many sideband audio endpoints are available.

The audio driver sends this request once with an output buffer size of zero (0) in order to determine the required output buffer size. In this case, the request will complete with Status STATUS_BUFFER_TOO_SMALL and set the <i>Information</i> member to the required buffer size. The audio driver then allocates the necessary storage space and sends the request again. Typically an audio driver will store a pointer to this storage location in its device context for reference during later activity.

The audio driver can then iteratively determine each endpoints capability with the IOCTL [IOCTL_SBAUD_GET_ENDPOINT_DESCRIPTOR](./ni-sidebandaudio-ioctl_sbaud_get_endpoint_descriptor.md).

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[sidebandaudio.h](index.md)

[Introduction to I/O Control Codes](/windows-hardware/drivers/kernel/introduction-to-i-o-control-codes)
