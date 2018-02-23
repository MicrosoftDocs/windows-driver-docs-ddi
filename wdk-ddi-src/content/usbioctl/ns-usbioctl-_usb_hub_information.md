---
UID: NS:usbioctl._USB_HUB_INFORMATION
title: "_USB_HUB_INFORMATION"
author: windows-driver-content
description: The USB_HUB_INFORMATION structure contains information about a hub.
old-location: buses\usb_hub_information.htm
old-project: UsbRef
ms.assetid: f65789b6-b2d1-4e5d-92b3-10730e76661a
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PUSB_HUB_INFORMATION, USB_HUB_INFORMATION, usbstrct_3997108b-7c0b-419e-80e8-fadab455a2f5.xml, _USB_HUB_INFORMATION, usbioctl/PUSB_HUB_INFORMATION, PUSB_HUB_INFORMATION, usbioctl/USB_HUB_INFORMATION, USB_HUB_INFORMATION structure [Buses], PUSB_HUB_INFORMATION structure pointer [Buses], buses.usb_hub_information"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbioctl.h
apiname:
-	USB_HUB_INFORMATION
product: Windows
targetos: Windows
req.typenames: USB_HUB_INFORMATION, *PUSB_HUB_INFORMATION
req.product: Windows 10 or later.
---

# _USB_HUB_INFORMATION structure


## -description


The <b>USB_HUB_INFORMATION</b> structure contains information about a hub.


## -syntax


````
typedef struct _USB_HUB_INFORMATION {
  USB_HUB_DESCRIPTOR HubDescriptor;
  BOOLEAN            HubIsBusPowered;
} USB_HUB_INFORMATION, *PUSB_HUB_INFORMATION;
````


## -struct-fields




### -field HubDescriptor

A <a href="..\usbspec\ns-usbspec-_usb_hub_descriptor.md">USB_HUB_DESCRIPTOR</a> structure that contains selected information from the hub descriptor.


### -field HubIsBusPowered

A Boolean value that indicates whether the hub is bus-powered. <b>TRUE</b>, the hub is bus-powered; <b>FALSE</b>, the hub is self-powered.


## -see-also

<a href="..\usbioctl\ns-usbioctl-_usb_node_information.md">USB_NODE_INFORMATION</a>



<a href="..\usbspec\ns-usbspec-_usb_hub_descriptor.md">USB_HUB_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_HUB_INFORMATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

