---
UID: NE:usbioctl._USB_HUB_TYPE
title: "_USB_HUB_TYPE"
author: windows-driver-content
description: The USB_HUB_TYPE enumeration defines constants that indicate the type of USB hub. The hub type is retrieved by the IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request.
old-location: buses\usb_hub_type.htm
old-project: usbref
ms.assetid: F7516B20-B30F-47BE-BBF3-AB5758D5CF73
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: USB_HUB_TYPE, USB_HUB_TYPE enumeration [Buses], Usb20Hub, Usb30Hub, UsbRootHub, _USB_HUB_TYPE, buses.usb_hub_type, usbioctl/USB_HUB_TYPE, usbioctl/Usb20Hub, usbioctl/Usb30Hub, usbioctl/UsbRootHub
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	usbioctl.h
api_name:
-	USB_HUB_TYPE
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# _USB_HUB_TYPE enumeration


## -description


The <b>USB_HUB_TYPE</b> enumeration defines constants that indicate the type of USB hub.

The hub type is retrieved by the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_information_ex.md">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request.

The request retrieves the hub descriptor associated with the specified hub in the <a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a> structure. The   <b>HubType</b> member contains a <b>USB_HUB_TYPE</b> enumerator that the application can use to evaluate the type of hub descriptor retrieved by the request. 


## -syntax


````
typedef enum _USB_HUB_TYPE { 
  UsbRootHub  = 1,
  Usb20Hub    = 2,
  Usb30Hub    = 3
} USB_HUB_TYPE;
````


## -enum-fields




### -field UsbRootHub

Indicates a root hub.


### -field Usb20Hub

Indicates that the retrieved hub descriptor is defined in USB 2.0 and 1.1 specifications.


### -field Usb30Hub

Indicates that the retrieved hub descriptor is defined in USB 3.0 specification.


## -see-also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_information_ex.md">IOCTL_USB_GET_HUB_INFORMATION_EX</a>



<a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>



 

 


