---
UID: NE:usbioctl._USB_HUB_TYPE
title: "_USB_HUB_TYPE"
author: windows-driver-content
description: The USB_HUB_TYPE enumeration defines constants that indicate the type of USB hub. The hub type is retrieved by the IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request.
old-location: buses\usb_hub_type.htm
old-project: usbref
ms.assetid: F7516B20-B30F-47BE-BBF3-AB5758D5CF73
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: Usb20Hub, Usb30Hub, buses.usb_hub_type, usbioctl/Usb20Hub, _USB_HUB_TYPE, USB_HUB_TYPE, usbioctl/USB_HUB_TYPE, usbioctl/UsbRootHub, UsbRootHub, USB_HUB_TYPE enumeration [Buses], usbioctl/Usb30Hub
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbioctl.h
apiname:
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>



<a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_information_ex.md">IOCTL_USB_GET_HUB_INFORMATION_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HUB_TYPE enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

