---
UID: NI:usbioctl.IOCTL_USB_GET_NODE_INFORMATION
title: IOCTL_USB_GET_NODE_INFORMATION (usbioctl.h)
description: The IOCTL_USB_GET_NODE_INFORMATION I/O control request is used with the USB_NODE_INFORMATION structure to retrieve information about a parent device.IOCTL_USB_GET_NODE_INFORMATION is a user-mode I/O control request.
old-location: buses\ioctl_usb_get_node_information.htm
tech.root: usbref
ms.assetid: b779cbf9-3021-4310-ae2e-e716bcc7b4c4
ms.date: 05/07/2018
ms.keywords: IOCTL_USB_GET_NODE_INFORMATION, IOCTL_USB_GET_NODE_INFORMATION control, IOCTL_USB_GET_NODE_INFORMATION control code [Buses], buses.ioctl_usb_get_node_information, usbioctl/IOCTL_USB_GET_NODE_INFORMATION, usbirp_123647fe-f02f-4961-aef8-1036be8727b8.xml
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
- Usbioctl.h
api_name:
- IOCTL_USB_GET_NODE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_NODE_INFORMATION IOCTL


## -description



The <b>IOCTL_USB_GET_NODE_INFORMATION</b> I/O control request is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540110">USB_NODE_INFORMATION</a> structure to retrieve information about a parent device.

<b>IOCTL_USB_GET_NODE_INFORMATION</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

On input, the <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540110">USB_NODE_INFORMATION</a> structure. On input, the <b>NodeType</b> member of this structure must indicate whether the parent device is a hub or a non-hub composite device.


### -input-buffer-length

The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540110">USB_NODE_INFORMATION</a> structure.


### -output-buffer

On output, <b>AssociatedIrp.SystemBuffer</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540110">USB_NODE_INFORMATION</a> structure that holds information about the parent device.


### -output-buffer-length

The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540110">USB_NODE_INFORMATION</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540110">USB_NODE_INFORMATION</a>
 

 

