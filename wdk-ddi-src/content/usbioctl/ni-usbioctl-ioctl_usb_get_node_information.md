---
UID: NI:usbioctl.IOCTL_USB_GET_NODE_INFORMATION
title: IOCTL_USB_GET_NODE_INFORMATION
author: windows-driver-content
description: The IOCTL_USB_GET_NODE_INFORMATION I/O control request is used with the USB_NODE_INFORMATION structure to retrieve information about a parent device.IOCTL_USB_GET_NODE_INFORMATION is a user-mode I/O control request.
old-location: buses\ioctl_usb_get_node_information.htm
old-project: usbref
ms.assetid: b779cbf9-3021-4310-ae2e-e716bcc7b4c4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_usb_get_node_information, IOCTL_USB_GET_NODE_INFORMATION control code [Buses], IOCTL_USB_GET_NODE_INFORMATION, usbioctl/IOCTL_USB_GET_NODE_INFORMATION, usbirp_123647fe-f02f-4961-aef8-1036be8727b8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Usbioctl.h
apiname: 
-	IOCTL_USB_GET_NODE_INFORMATION
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_NODE_INFORMATION IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The <b>IOCTL_USB_GET_NODE_INFORMATION</b> I/O control request is used with the <a href="..\usbioctl\ns-usbioctl-_usb_node_information.md">USB_NODE_INFORMATION</a> structure to retrieve information about a parent device.

<b>IOCTL_USB_GET_NODE_INFORMATION</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

On input, the <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\usbioctl\ns-usbioctl-_usb_node_information.md">USB_NODE_INFORMATION</a> structure. On input, the <b>NodeType</b> member of this structure must indicate whether the parent device is a hub or a non-hub composite device.


### -input-buffer-length

The size of a <a href="..\usbioctl\ns-usbioctl-_usb_node_information.md">USB_NODE_INFORMATION</a> structure.


### -output-buffer

On output, <b>AssociatedIrp.SystemBuffer</b> points to a <a href="..\usbioctl\ns-usbioctl-_usb_node_information.md">USB_NODE_INFORMATION</a> structure that holds information about the parent device.


### -output-buffer-length

The size of a <a href="..\usbioctl\ns-usbioctl-_usb_node_information.md">USB_NODE_INFORMATION</a> structure.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -see-also

<a href="..\usbioctl\ns-usbioctl-_usb_node_information.md">USB_NODE_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_GET_NODE_INFORMATION control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

