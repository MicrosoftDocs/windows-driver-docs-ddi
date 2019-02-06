---
UID: NE:usbioctl._USB_HUB_NODE
title: _USB_HUB_NODE (usbioctl.h)
description: The USB_HUB_NODE enumerator indicates whether a device is a hub or a composite device.
old-location: buses\usb_hub_node.htm
tech.root: usbref
ms.assetid: fdd69121-2b3c-4394-b67e-c29f43daf113
ms.date: 05/07/2018
ms.keywords: USB_HUB_NODE, USB_HUB_NODE enumeration [Buses], UsbHub, UsbMIParent, _USB_HUB_NODE, buses.usb_hub_node, usbioctl/USB_HUB_NODE, usbioctl/UsbHub, usbioctl/UsbMIParent, usbstrct_9dadc1ba-6775-48d3-8ebf-fa42ad6992bf.xml
ms.topic: enum
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
-	USB_HUB_NODE
product:
- Windows
targetos: Windows
req.typenames: USB_HUB_NODE
---

# _USB_HUB_NODE enumeration


## -description


The <b>USB_HUB_NODE</b> enumerator indicates whether a device is a hub or a composite device.


## -enum-fields




### -field UsbHub

Indicates that the device is a hub.


### -field UsbMIParent

Indicates that the device is a composite device with multiple interfaces.


## -remarks



Composite devices are devices that have multiple interfaces. Windows loads the USB generic parent driver for composite devices, instead of the hub driver, but the generic parent driver performs many of the functions of the hub driver. It creates a child PDO for each interface, as though the interface were a separate device.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540110">USB_NODE_INFORMATION</a>
 

 

