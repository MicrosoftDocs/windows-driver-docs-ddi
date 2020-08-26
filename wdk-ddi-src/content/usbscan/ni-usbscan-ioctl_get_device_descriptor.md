---
UID: NI:usbscan.IOCTL_GET_DEVICE_DESCRIPTOR
title: IOCTL_GET_DEVICE_DESCRIPTOR (usbscan.h)
description: Returns vendor and device identifiers.
old-location: image\ioctl_get_device_descriptor.htm
tech.root: image
ms.assetid: a6946dd4-db72-477f-bf2c-958c363340a0
ms.date: 05/03/2018
keywords: ["IOCTL_GET_DEVICE_DESCRIPTOR IOCTL"]
ms.keywords: IOCTL_GET_DEVICE_DESCRIPTOR, IOCTL_GET_DEVICE_DESCRIPTOR control, IOCTL_GET_DEVICE_DESCRIPTOR control code [Imaging Devices], image.ioctl_get_device_descriptor, stifnc_b84c2743-6548-40c7-8b97-4952867740ad.xml, usbscan/IOCTL_GET_DEVICE_DESCRIPTOR
f1_keywords:
 - "usbscan/IOCTL_GET_DEVICE_DESCRIPTOR"
 - "IOCTL_GET_DEVICE_DESCRIPTOR"
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbscan.h
api_name:
- IOCTL_GET_DEVICE_DESCRIPTOR
targetos: Windows
req.typenames: 
---

# IOCTL_GET_DEVICE_DESCRIPTOR IOCTL


## -description


Returns vendor and device identifiers.


## -ioctlparameters




### -input-buffer

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_device_descriptor">DEVICE_DESCRIPTOR</a> structure.


### -input-buffer-length

Size of the input buffer.


### -output-buffer

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_device_descriptor">DEVICE_DESCRIPTOR</a> structure (same as <i>lpInbuffer</i>).


### -output-buffer-length

Size of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="ddk_ioctl_get_device_descriptor_si"></a><a id="DDK_IOCTL_GET_DEVICE_DESCRIPTOR_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_GET_USB_DESCRIPTOR I/O control code, the caller must specify the address of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_device_descriptor">DEVICE_DESCRIPTOR</a> structure as the function's <i>lpOutbuffer</i> parameter. The kernel-mode driver fills in the structure.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices">Accessing Kernel-Mode Drivers for Still Image Devices</a>.



