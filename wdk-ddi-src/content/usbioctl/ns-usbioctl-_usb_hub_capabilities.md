---
UID: NS:usbioctl._USB_HUB_CAPABILITIES
title: "_USB_HUB_CAPABILITIES"
author: windows-driver-content
description: The USB_HUB_CAPABILITIES structure has been deprecated. Use USB_HUB_CAPABILITIES_EX instead.
old-location: buses\usb_hub_capabilities.htm
old-project: usbref
ms.assetid: a87f747f-474d-401d-9757-0820680e5c8e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_HUB_CAPABILITIES, PUSB_HUB_CAPABILITIES, PUSB_HUB_CAPABILITIES structure pointer [Buses], USB_HUB_CAPABILITIES, USB_HUB_CAPABILITIES structure [Buses], _USB_HUB_CAPABILITIES, buses.usb_hub_capabilities, usbioctl/PUSB_HUB_CAPABILITIES, usbioctl/USB_HUB_CAPABILITIES, usbstrct_b82d8bad-3ed4-40d1-a6c1-7ac416ebf157.xml"
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
-	USB_HUB_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: USB_HUB_CAPABILITIES, *PUSB_HUB_CAPABILITIES
req.product: Windows 10 or later.
---

# _USB_HUB_CAPABILITIES structure


## -description


The <b>USB_HUB_CAPABILITIES</b> structure has been deprecated. Use <a href="..\usbioctl\ns-usbioctl-_usb_hub_capabilities_ex.md">USB_HUB_CAPABILITIES_EX</a> instead.


## -syntax


````
typedef struct _USB_HUB_CAPABILITIES {
  ULONG HubIs2xCapable  :1;
} USB_HUB_CAPABILITIES, *PUSB_HUB_CAPABILITIES;
````


## -struct-fields




### -field HubIs2xCapable

If <b>TRUE</b>, the hub is capable of running at high speed.


## -see-also

<a href="..\usbioctl\ns-usbioctl-_usb_hub_cap_flags.md">USB_HUB_CAP_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbioctl\ns-usbioctl-_usb_hub_capabilities_ex.md">USB_HUB_CAPABILITIES_EX</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_capabilities.md">IOCTL_USB_GET_HUB_CAPABILITIES</a>



 

 


