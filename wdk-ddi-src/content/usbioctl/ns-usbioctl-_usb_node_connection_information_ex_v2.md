---
UID: NS:usbioctl._USB_NODE_CONNECTION_INFORMATION_EX_V2
title: "_USB_NODE_CONNECTION_INFORMATION_EX_V2"
author: windows-driver-content
description: The USB_NODE_CONNECTION_INFORMATION_EX_V2 structure is used with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2 I/O control request to retrieve speed information about a Universal Serial Bus (USB) device that is attached to a particular port.
old-location: buses\_usb_node_connection_information_ex_v2.htm
old-project: usbref
ms.assetid: F886F470-BAAB-41C6-8431-01BF99236F81
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PUSB_NODE_CONNECTION_INFORMATION_EX_V2, PUSB_NODE_CONNECTION_INFORMATION_EX_V2, PUSB_NODE_CONNECTION_INFORMATION_EX_V2 structure pointer [Buses], USB_NODE_CONNECTION_INFORMATION_EX_V2, USB_NODE_CONNECTION_INFORMATION_EX_V2 structure [Buses], _USB_NODE_CONNECTION_INFORMATION_EX_V2, buses._usb_node_connection_information_ex_v2, usbioctl/PUSB_NODE_CONNECTION_INFORMATION_EX_V2, usbioctl/USB_NODE_CONNECTION_INFORMATION_EX_V2"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	USB_NODE_CONNECTION_INFORMATION_EX_V2
product: Windows
targetos: Windows
req.typenames: USB_NODE_CONNECTION_INFORMATION_EX_V2, *PUSB_NODE_CONNECTION_INFORMATION_EX_V2
---

# _USB_NODE_CONNECTION_INFORMATION_EX_V2 structure


## -description


The <b>USB_NODE_CONNECTION_INFORMATION_EX_V2</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450861">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> I/O control request to retrieve speed information about a Universal Serial Bus (USB) device that is attached to a particular port.


## -struct-fields




### -field ConnectionIndex

The port number. If there are <i>n</i> ports on the USB hub, the ports are numbered from 1 to <i>n</i>. To get the number of ports, send the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450860">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request. The request retrieves the highest port number on the hub.


### -field Length

The number of bytes that are required to hold the <b>USB_NODE_CONNECTION_INFORMATION_EX_V2</b> structure. The value must be set by the caller as input to  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450861">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> request.


### -field SupportedUsbProtocols

The USB signaling protocols that are supported by the port. 

In the caller's <a href="https://msdn.microsoft.com/library/windows/hardware/hh450861">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> request, the caller can set <b>SupportedUsbProtocols</b> to a bitwise <b>OR</b> of one or more flags defined in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406267">USB_PROTOCOLS</a>.

Upon completion of the request, <b>SupportedUsbProtocols</b> contains flags, which indicate the protocols that are actually supported by the port.


### -field Flags

A bitmask that indicates the properties and capabilities of the attached device or  port. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406264">USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450861">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406264">USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS</a>
 

 

