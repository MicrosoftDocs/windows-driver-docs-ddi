---
UID: NI:usbioctl.IOCTL_USB_GET_HUB_CAPABILITIES_EX
title: IOCTL_USB_GET_HUB_CAPABILITIES_EX (usbioctl.h)
description: The IOCTL_USB_GET_HUB_CAPABILITIES_EX I/O control request retrieves the capabilities of a USB hub.IOCTL_USB_GET_HUB_CAPABILITIES_EX is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).
old-location: buses\ioctl_usb_get_hub_capabilities_ex.htm
tech.root: usbref
ms.assetid: 49c25f30-8eff-4894-8a82-a90c5a7d9aa4
ms.date: 05/07/2018
ms.keywords: IOCTL_USB_GET_HUB_CAPABILITIES_EX, IOCTL_USB_GET_HUB_CAPABILITIES_EX control, IOCTL_USB_GET_HUB_CAPABILITIES_EX control code [Buses], buses.ioctl_usb_get_hub_capabilities_ex, usbioctl/IOCTL_USB_GET_HUB_CAPABILITIES_EX, usbirp_bed6a9f5-00ee-4f0b-9906-cd27d85a74c2.xml
f1_keywords:
 - "usbioctl/IOCTL_USB_GET_HUB_CAPABILITIES_EX"
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later.
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
- Usbioctl.h
api_name:
- IOCTL_USB_GET_HUB_CAPABILITIES_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_HUB_CAPABILITIES_EX IOCTL


## -description



The <b>IOCTL_USB_GET_HUB_CAPABILITIES_EX</b> I/O control request retrieves the capabilities of a USB hub.

<b>IOCTL_USB_GET_HUB_CAPABILITIES_EX</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a user-allocated buffer.


### -input-buffer-length

 The buffer length equals <code>sizeof(USB_HUB_CAPABILITIES_EX)</code>.


### -output-buffer

<b>AssociatedIrp.SystemBuffer</b> points to a user-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_capabilities_ex">USB_HUB_CAPABILITIES_EX</a> structure. On output, this structure describes the hub capabilities. 


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the data that is returned at <b>SystemBuffer</b>, or <code>sizeof(USB_HUB_CAPABILITIES_EX)</code>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The USB stack sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES. If the hub has not been started or is not functional, the request returns STATUS_UNSUCCESSFUL.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_capabilities_ex">USB_HUB_CAPABILITIES_EX</a>
 

 

