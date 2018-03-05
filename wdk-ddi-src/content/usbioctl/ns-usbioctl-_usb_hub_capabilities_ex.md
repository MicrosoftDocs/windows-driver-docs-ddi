---
UID: NS:usbioctl._USB_HUB_CAPABILITIES_EX
title: "_USB_HUB_CAPABILITIES_EX"
author: windows-driver-content
description: The USB_HUB_CAPABILITIES_EX structure is used with the IOCTL_USB_GET_HUB_CAPABILITIES I/O control request to retrieve the capabilities of a particular USB hub.
old-location: buses\usb_hub_capabilities_ex.htm
old-project: usbref
ms.assetid: deb8d710-6137-4f69-8fde-00d46cdb6f4f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_HUB_CAPABILITIES_EX, PUSB_HUB_CAPABILITIES_EX, PUSB_HUB_CAPABILITIES_EX structure pointer [Buses], USB_HUB_CAPABILITIES_EX, USB_HUB_CAPABILITIES_EX structure [Buses], _USB_HUB_CAPABILITIES_EX, buses.usb_hub_capabilities_ex, usbioctl/PUSB_HUB_CAPABILITIES_EX, usbioctl/USB_HUB_CAPABILITIES_EX, usbstrct_42446556-393a-4d58-934e-f63d62fa3c07.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
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
-	USB_HUB_CAPABILITIES_EX
product: Windows
targetos: Windows
req.typenames: USB_HUB_CAPABILITIES_EX, *PUSB_HUB_CAPABILITIES_EX
req.product: Windows 10 or later.
---

# _USB_HUB_CAPABILITIES_EX structure


## -description


The <b>USB_HUB_CAPABILITIES_EX</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_capabilities.md">IOCTL_USB_GET_HUB_CAPABILITIES</a> I/O control request to retrieve the capabilities of a particular USB hub.


## -syntax


````
typedef struct _USB_HUB_CAPABILITIES_EX {
  USB_HUB_CAP_FLAGS CapabilityFlags;
} USB_HUB_CAPABILITIES_EX, *PUSB_HUB_CAPABILITIES_EX;
````


## -struct-fields




### -field CapabilityFlags

A <a href="..\usbioctl\ns-usbioctl-_usb_hub_cap_flags.md">USB_HUB_CAP_FLAGS</a> structure that reports the hub capabilities.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbioctl\ns-usbioctl-_usb_hub_cap_flags.md">USB_HUB_CAP_FLAGS</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_capabilities.md">IOCTL_USB_GET_HUB_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HUB_CAPABILITIES_EX structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

