---
UID: NI:usbioctl.IOCTL_USB_GET_HUB_INFORMATION_EX
title: IOCTL_USB_GET_HUB_INFORMATION_EX (usbioctl.h)
description: The IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request is sent by an application to retrieve information about a USB hub in a USB_HUB_INFORMATION_EX structure.The request retrieves the highest port number on the hub.
old-location: buses\ioctl_usb_get_hub_information_ex.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_USB_GET_HUB_INFORMATION_EX IOCTL"]
ms.keywords: IOCTL_USB_GET_HUB_INFORMATION_EX, IOCTL_USB_GET_HUB_INFORMATION_EX control, IOCTL_USB_GET_HUB_INFORMATION_EX control code [Buses], buses.ioctl_usb_get_hub_information_ex, usbioctl/IOCTL_USB_GET_HUB_INFORMATION_EX
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_USB_GET_HUB_INFORMATION_EX
 - usbioctl/IOCTL_USB_GET_HUB_INFORMATION_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - IOCTL_USB_GET_HUB_INFORMATION_EX
---

# IOCTL_USB_GET_HUB_INFORMATION_EX IOCTL


## -description

The <b>IOCTL_USB_GET_HUB_INFORMATION_EX</b> I/O control request is sent by an application to retrieve information about a USB hub in a <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information_ex">USB_HUB_INFORMATION_EX</a> structure.

The request retrieves the highest port number on the hub. For USB 2.0 and SuperSpeed hubs (non-root hubs), the request also retrieves the associated hub descriptors, as defined in USB 2.0 and 3.0 Specifications, respectively. 

<b>IOCTL_USB_GET_HUB_INFORMATION_EX</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

<b>AssociatedIrp.SystemBuffer</b> points to a caller-allocated    <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information_ex">USB_HUB_INFORMATION_EX</a> structure.

### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member indicates the size, in bytes, of the caller-allocated buffer whose size equals <code>sizeof(USB_HUB_INFORMATION_EX)</code>.

### -output-buffer

 On output, the <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information_ex">USB_HUB_INFORMATION_EX</a> structure that is pointed to by  <b>AssociatedIrp.SystemBuffer</b> is filled with information about the hub.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the output buffer <b>SystemBuffer</b>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The USB stack sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB driver stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information_ex">USB_HUB_INFORMATION_EX</a>
