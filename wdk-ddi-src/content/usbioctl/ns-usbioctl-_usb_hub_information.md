---
UID: NS:usbioctl._USB_HUB_INFORMATION
title: _USB_HUB_INFORMATION (usbioctl.h)
description: The USB_HUB_INFORMATION structure contains information about a hub.
old-location: buses\usb_hub_information.htm
tech.root: usbref
ms.assetid: f65789b6-b2d1-4e5d-92b3-10730e76661a
ms.date: 05/07/2018
keywords: ["_USB_HUB_INFORMATION structure"]
ms.keywords: "*PUSB_HUB_INFORMATION, PUSB_HUB_INFORMATION, PUSB_HUB_INFORMATION structure pointer [Buses], USB_HUB_INFORMATION, USB_HUB_INFORMATION structure [Buses], _USB_HUB_INFORMATION, buses.usb_hub_information, usbioctl/PUSB_HUB_INFORMATION, usbioctl/USB_HUB_INFORMATION, usbstrct_3997108b-7c0b-419e-80e8-fadab455a2f5.xml"
f1_keywords:
 - "usbioctl/USB_HUB_INFORMATION"
 - "USB_HUB_INFORMATION"
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
- usbioctl.h
api_name:
- USB_HUB_INFORMATION
targetos: Windows
req.typenames: USB_HUB_INFORMATION, *PUSB_HUB_INFORMATION
---

# _USB_HUB_INFORMATION structure


## -description


The <b>USB_HUB_INFORMATION</b> structure contains information about a hub.


## -struct-fields




### -field HubDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_hub_descriptor">USB_HUB_DESCRIPTOR</a> structure that contains selected information from the hub descriptor.


### -field HubIsBusPowered

A Boolean value that indicates whether the hub is bus-powered. <b>TRUE</b>, the hub is bus-powered; <b>FALSE</b>, the hub is self-powered.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_hub_descriptor">USB_HUB_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_information">USB_NODE_INFORMATION</a>
 

 

