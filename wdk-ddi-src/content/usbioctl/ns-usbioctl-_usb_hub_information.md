---
UID: NS:usbioctl._USB_HUB_INFORMATION
title: "_USB_HUB_INFORMATION"
author: windows-driver-content
description: The USB_HUB_INFORMATION structure contains information about a hub.
old-location: buses\usb_hub_information.htm
old-project: usbref
ms.assetid: f65789b6-b2d1-4e5d-92b3-10730e76661a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_HUB_INFORMATION, PUSB_HUB_INFORMATION, PUSB_HUB_INFORMATION structure pointer [Buses], USB_HUB_INFORMATION, USB_HUB_INFORMATION structure [Buses], _USB_HUB_INFORMATION, buses.usb_hub_information, usbioctl/PUSB_HUB_INFORMATION, usbioctl/USB_HUB_INFORMATION, usbstrct_3997108b-7c0b-419e-80e8-fadab455a2f5.xml"
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_HUB_INFORMATION
product: Windows
targetos: Windows
req.typenames: USB_HUB_INFORMATION, *PUSB_HUB_INFORMATION
req.product: Windows 10 or later.
---

# _USB_HUB_INFORMATION structure


## -description


The <b>USB_HUB_INFORMATION</b> structure contains information about a hub.


## -struct-fields




### -field HubDescriptor

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff539331">USB_HUB_DESCRIPTOR</a> structure that contains selected information from the hub descriptor.


### -field HubIsBusPowered

A Boolean value that indicates whether the hub is bus-powered. <b>TRUE</b>, the hub is bus-powered; <b>FALSE</b>, the hub is self-powered.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539331">USB_HUB_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540110">USB_NODE_INFORMATION</a>
 

 

