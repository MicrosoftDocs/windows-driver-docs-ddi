---
UID: NS:usbioctl._USB_NODE_CONNECTION_INFORMATION_EX_V2
title: "_USB_NODE_CONNECTION_INFORMATION_EX_V2"
author: windows-driver-content
description: The USB_NODE_CONNECTION_INFORMATION_EX_V2 structure is used with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2 I/O control request to retrieve speed information about a Universal Serial Bus (USB) device that is attached to a particular port.
old-location: buses\_usb_node_connection_information_ex_v2.htm
old-project: usbref
ms.assetid: F886F470-BAAB-41C6-8431-01BF99236F81
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PUSB_NODE_CONNECTION_INFORMATION_EX_V2, ,, 2, A, B, C, D, E, F, I, M, N, O, P, PUSB_NODE_CONNECTION_INFORMATION_EX_V2, PUSB_NODE_CONNECTION_INFORMATION_EX_V2 structure pointer [Buses], R, S, T, U, USB_NODE_CONNECTION_INFORMATION_EX_V2, USB_NODE_CONNECTION_INFORMATION_EX_V2 structure [Buses], V, X, _, _USB_NODE_CONNECTION_INFORMATION_EX_V2, buses._usb_node_connection_information_ex_v2, usbioctl/PUSB_NODE_CONNECTION_INFORMATION_EX_V2, usbioctl/USB_NODE_CONNECTION_INFORMATION_EX_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	USB_NODE_CONNECTION_INFORMATION_EX_V2
product: Windows
targetos: Windows
req.typenames: USB_NODE_CONNECTION_INFORMATION_EX_V2, *PUSB_NODE_CONNECTION_INFORMATION_EX_V2
req.product: Windows 10 or later.
---

# _USB_NODE_CONNECTION_INFORMATION_EX_V2 structure


## -description


The <b>USB_NODE_CONNECTION_INFORMATION_EX_V2</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> I/O control request to retrieve speed information about a Universal Serial Bus (USB) device that is attached to a particular port.


## -syntax


````
typedef struct _USB_NODE_CONNECTION_INFORMATION_EX_V2 {
  ULONG                                       ConnectionIndex;
  ULONG                                       Length;
  USB_PROTOCOLS                               SupportedUsbProtocols;
  USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS Flags;
} USB_NODE_CONNECTION_INFORMATION_EX_V2, *PUSB_NODE_CONNECTION_INFORMATION_EX_V2;
````


## -struct-fields




### -field ConnectionIndex

The port number. If there are <i>n</i> ports on the USB hub, the ports are numbered from 1 to <i>n</i>. To get the number of ports, send the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_information_ex.md">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request. The request retrieves the highest port number on the hub.


### -field Length

The number of bytes that are required to hold the <b>USB_NODE_CONNECTION_INFORMATION_EX_V2</b> structure. The value must be set by the caller as input to  the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> request.


### -field SupportedUsbProtocols

The USB signaling protocols that are supported by the port. 

In the caller's <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> request, the caller can set <b>SupportedUsbProtocols</b> to a bitwise <b>OR</b> of one or more flags defined in <a href="..\usbioctl\ns-usbioctl-_usb_protocols.md">USB_PROTOCOLS</a>.

Upon completion of the request, <b>SupportedUsbProtocols</b> contains flags, which indicate the protocols that are actually supported by the port.


### -field Flags

A bitmask that indicates the properties and capabilities of the attached device or  port. For more information, see <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information_ex_v2_flags.md">USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS</a>.


## -see-also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a>



<a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information_ex_v2_flags.md">USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_NODE_CONNECTION_INFORMATION_EX_V2 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

