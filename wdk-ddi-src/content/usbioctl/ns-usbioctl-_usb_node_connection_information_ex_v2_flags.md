---
UID: NS:usbioctl._USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS
title: _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS (usbioctl.h)
description: The USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS union is used to indicate the speed at which a USB 3.0 device is currently operating and whether it can operate at higher speed, when attached to a particular port.
old-location: buses\usb_node_connection_information_ex_v2_flags.htm
tech.root: usbref
ms.assetid: F066CE0E-3247-4C42-9EF6-8A6EB0C0BC71
ms.date: 05/07/2018
keywords: ["USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS structure"]
ms.keywords: "*PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS union pointer [Buses], USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS union [Buses], _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, buses.usb_node_connection_information_ex_v2_flags, usbioctl/PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, usbioctl/USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS"
f1_keywords:
 - "usbioctl/USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS"
 - "USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS
targetos: Windows
req.typenames: USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, *PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS
---

# _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS structure


## -description


The <b>USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS</b> union is used to indicate the speed at which a USB 3.0  device is currently operating and whether it can operate at higher speed, when attached to a particular port. 

Device speed information is obtained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_information_ex_v2">USB_NODE_CONNECTION_INFORMATION_EX_V2</a> structure by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> I/O control request.

Or: the speed in which a device attached to a port is currently operating and at what speeds it is capable of operating.


## -struct-fields




### -field ul

A bitmask that indicates the USB speed of the device that is attached to the port.


### -field DeviceIsOperatingAtSuperSpeedOrHigher

If <b>TRUE</b>, the attached device is currently operating at SuperSpeed or a higher speed that is defined by the official USB specification. 


### -field DeviceIsSuperSpeedCapableOrHigher

If <b>TRUE</b>, the attached device is a USB 3.0 device and is capable of operating at SuperSpeed or a higher speed that is defined by the official USB specification.


### -field DeviceIsOperatingAtSuperSpeedPlusOrHigher

 


### -field DeviceIsSuperSpeedPlusCapableOrHigher

 


### -field ReservedMBZ

Reserved. Do not use.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_information_ex_v2_flags">USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS</a>
 

 

