---
UID: NS:usbioctl._USB_HUB_INFORMATION_EX
title: "_USB_HUB_INFORMATION_EX"
author: windows-driver-content
description: The USB_HUB_INFORMATION_EX structure is used with the IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request to retrieve information about a Universal Serial Bus (USB) hub.
old-location: buses\usb_hub_information_ex.htm
old-project: usbref
ms.assetid: 23E99282-16BD-4E1E-9419-C1F44B913C4F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_HUB_INFORMATION_EX, PUSB_HUB_INFORMATION_EX, PUSB_HUB_INFORMATION_EX structure pointer [Buses], USB_HUB_INFORMATION_EX, USB_HUB_INFORMATION_EX structure [Buses], _USB_HUB_INFORMATION_EX, buses.usb_hub_information_ex, usbioctl/PUSB_HUB_INFORMATION_EX, usbioctl/USB_HUB_INFORMATION_EX"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_HUB_INFORMATION_EX
product: Windows
targetos: Windows
req.typenames: USB_HUB_INFORMATION_EX, *PUSB_HUB_INFORMATION_EX
req.product: Windows 10 or later.
---

# _USB_HUB_INFORMATION_EX structure


## -description


The <b>USB_HUB_INFORMATION_EX</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450860">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request to retrieve information about a  Universal Serial Bus (USB) hub.


## -struct-fields




### -field HubType

The type of hub: root hub, USB 2.0, or USB 3.0 hub. On successful completion of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450860">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request, <b>HubType</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406263">USB_HUB_TYPE</a> enumerator that indicates the type of hub.




### -field HighestPortNumber

Indicates the number of ports on the hub. The ports are numbered from 1 to <b>HighestPortNumber</b>, where <b>HighestPortNumber</b> is the highest valid port number on the hub.


### -field u



#### UsbHubDescriptor

If <b>HubType</b> indicates a USB 2.0 hub,  <b>u.UsbHubDescriptor</b> is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539331">USB_HUB_DESCRIPTOR</a> structure that contains selected information from the USB 2.0/1.1 hub descriptor, as defined in the USB 2.0 Specification. 



#### Usb30HubDescriptor

If <b>HubType</b> indicates a USB 3.0 hub,  <b>u.UsbHub30Descriptor</b> is a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406254">USB_30_HUB_DESCRIPTOR</a> structure that contains selected information from the USB 3.0 hub descriptor, as defined in the USB 3.0 Specification.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450860">IOCTL_USB_GET_HUB_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406254">USB_30_HUB_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539331">USB_HUB_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406263">USB_HUB_TYPE</a>
 

 

