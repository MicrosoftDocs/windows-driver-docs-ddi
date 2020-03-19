---
UID: NI:usbscan.IOCTL_GET_USB_DESCRIPTOR
title: IOCTL_GET_USB_DESCRIPTOR (usbscan.h)
description: Returns a specified USB Descriptor.
old-location: image\ioctl_get_usb_descriptor.htm
tech.root: image
ms.assetid: a5490a2a-d406-4029-b8be-446236a936bb
ms.date: 05/03/2018
keywords: ["IOCTL_GET_USB_DESCRIPTOR IOCTL"]
ms.keywords: IOCTL_GET_USB_DESCRIPTOR, IOCTL_GET_USB_DESCRIPTOR control, IOCTL_GET_USB_DESCRIPTOR control code [Imaging Devices], image.ioctl_get_usb_descriptor, stifnc_9d8ca100-d268-4e51-88fb-925e0a029ece.xml, usbscan/IOCTL_GET_USB_DESCRIPTOR
f1_keywords:
 - "usbscan/IOCTL_GET_USB_DESCRIPTOR"
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
- IOCTL_GET_USB_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GET_USB_DESCRIPTOR IOCTL


## -description


Returns a specified USB Descriptor.


## -ioctlparameters




### -input-buffer

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_usbscan_get_descriptor">USBSCAN_GET_DESCRIPTOR</a> structure.


### -input-buffer-length

Size of the input buffer.


### -output-buffer

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_string_descriptor">USB_STRING_DESCRIPTOR</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure.


### -output-buffer-length

Size of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="ddk_ioctl_get_usb_descriptor_si"></a><a id="DDK_IOCTL_GET_USB_DESCRIPTOR_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_GET_USB_DESCRIPTOR I/O control code, the caller must specify the address of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_usbscan_get_descriptor">USBSCAN_GET_DESCRIPTOR</a> structure as the function's <i>lpInBuffer</i> parameter. Depending on the value specified for the <b>DescriptorType</b> member of the USBSCAN_GET_DESCRIPTOR structure, the function's <i>lpOutbuffer</i> parameter must point to either a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_string_descriptor">USB_STRING_DESCRIPTOR</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure.

The kernel-mode driver obtains a USB descriptor by calling <a href="https://docs.microsoft.com/previous-versions/ff538943(v=vs.85)">UsbBuildGetDescriptorRequest</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices">Accessing Kernel-Mode Drivers for Still Image Devices</a>.

For more information about USB descriptors, see the <i>Universal Serial Bus Specification</i>.



