---
UID: NE:usbioctl._USB_HUB_NODE
title: _USB_HUB_NODE
author: windows-driver-content
description: The USB_HUB_NODE enumerator indicates whether a device is a hub or a composite device.
old-location: buses\usb_hub_node.htm
old-project: usbref
ms.assetid: fdd69121-2b3c-4394-b67e-c29f43daf113
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usbioctl/USB_HUB_NODE, UsbHub, _USB_HUB_NODE, usbioctl/UsbMIParent, usbstrct_9dadc1ba-6775-48d3-8ebf-fa42ad6992bf.xml, UsbMIParent, USB_HUB_NODE, USB_HUB_NODE enumeration [Buses], buses.usb_hub_node, usbioctl/UsbHub
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	usbioctl.h
apiname: 
-	USB_HUB_NODE
product: Windows
targetos: Windows
req.typenames: USB_HUB_NODE
req.product: Windows 10 or later.
---

# _USB_HUB_NODE enumeration


## -description


The <b>USB_HUB_NODE</b> enumerator indicates whether a device is a hub or a composite device.


## -syntax


````
typedef enum _USB_HUB_NODE { 
  UsbHub       = 0,
  UsbMIParent  = 1
} USB_HUB_NODE;
````


## -enum-fields




### -field UsbHub

Indicates that the device is a hub.


### -field UsbMIParent

Indicates that the device is a composite device with multiple interfaces.


## -remarks


Composite devices are devices that have multiple interfaces. Windows loads the USB generic parent driver for composite devices, instead of the hub driver, but the generic parent driver performs many of the functions of the hub driver. It creates a child PDO for each interface, as though the interface were a separate device.



## -see-also

<a href="..\usbioctl\ns-usbioctl-_usb_node_information.md">USB_NODE_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HUB_NODE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

