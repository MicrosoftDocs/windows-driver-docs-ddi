---
UID: NS:usbioctl._USB_NODE_CONNECTION_NAME
title: "_USB_NODE_CONNECTION_NAME"
author: windows-driver-content
description: The USB_NODE_CONNECTION_NAME structure is used with the IOCTL_USB_GET_NODE_CONNECTION_NAME I/O control request to retrieve the symbolic link of the downstream hub that is attached to the port.
old-location: buses\usb_node_connection_name.htm
old-project: usbref
ms.assetid: f38248fb-b2aa-417a-9d9b-36ff069bf78f
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PUSB_NODE_CONNECTION_NAME, PUSB_NODE_CONNECTION_NAME, PUSB_NODE_CONNECTION_NAME structure pointer [Buses], USB_NODE_CONNECTION_NAME, USB_NODE_CONNECTION_NAME structure [Buses], _USB_NODE_CONNECTION_NAME, buses.usb_node_connection_name, usbioctl/PUSB_NODE_CONNECTION_NAME, usbioctl/USB_NODE_CONNECTION_NAME, usbstrct_51cb29d4-aac8-4138-bddd-908f9859bad3.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_NODE_CONNECTION_NAME
product:
- Windows
targetos: Windows
req.typenames: USB_NODE_CONNECTION_NAME, *PUSB_NODE_CONNECTION_NAME
---

# _USB_NODE_CONNECTION_NAME structure


## -description


The <b>USB_NODE_CONNECTION_NAME</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537323">IOCTL_USB_GET_NODE_CONNECTION_NAME</a> I/O control request to retrieve the symbolic link of the downstream hub that is attached to the port.


## -struct-fields




### -field ConnectionIndex

A value that is greater than or equal to 1 that specifies the number of the port to which the hub is attached.


### -field ActualLength

The length, in bytes, of the attached hub's symbolic link.


### -field NodeName

A Unicode symbolic link for the downstream hub that is attached to the port that is indicated by <b>ConnectionIndex</b>. If there is no attached device, the attached device does not have a symbolic link, or if the device is not a hub, <b>NodeName</b>[0] will contain a value of UNICODE_NULL.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537323">IOCTL_USB_GET_NODE_CONNECTION_NAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
 

 

