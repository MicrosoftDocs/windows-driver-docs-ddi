---
UID: NI:usbioctl.IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION
title: IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION
author: windows-driver-content
description: The IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION I/O control request retrieves one or more descriptors for the device that is associated with the indicated port index.IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION is a user-mode I/O control request.
old-location: buses\ioctl_usb_get_descriptor_from_node_connection.htm
old-project: usbref
ms.assetid: 60b41f73-ef12-4d3f-9df4-8958ab66bf14
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_HUB_TYPE, USB_HUB_TYPE
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
req.alt-api: IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION
req.alt-loc: Usbioctl.h
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
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION IOCTL



## -description

The <b>IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</b> I/O control request retrieves one or more descriptors for the device that is associated with the indicated port index.

<b>IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).



The <b>IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</b> I/O control request retrieves one or more descriptors for the device that is associated with the indicated port index.

<b>IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).



## -ioctlparameters

### -input-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\usbioctl\ns-usbioctl-_usb_descriptor_request.md">USB_DESCRIPTOR_REQUEST</a> structure that describes the descriptor request. 


### -input-buffer-length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the user-allocated output buffer in the <b>Data</b> member of the <a href="..\usbioctl\ns-usbioctl-_usb_descriptor_request.md">USB_DESCRIPTOR_REQUEST</a> structure. 


### -output-buffer
The <b>Data</b> member of the <a href="..\usbioctl\ns-usbioctl-_usb_descriptor_request.md">USB_DESCRIPTOR_REQUEST</a> structure at <b>AssociatedIrp.SystemBuffer</b> points to the output buffer.


### -output-buffer-length


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\usbioctl\ns-usbioctl-_usb_descriptor_request.md">USB_DESCRIPTOR_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

