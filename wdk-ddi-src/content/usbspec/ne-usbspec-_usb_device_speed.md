---
UID: NE:usbspec._USB_DEVICE_SPEED
title: "_USB_DEVICE_SPEED"
author: windows-driver-content
description: The USB_DEVICE_SPEED enumeration defines constants for USB device speeds.
old-location: buses\usb_device_speed.htm
old-project: usbref
ms.assetid: e7c50bac-96ca-446d-a865-4ad87ad5b295
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: USB_DEVICE_SPEED, USB_DEVICE_SPEED enumeration [Buses], usbspec/UsbLowSpeed, UsbSuperSpeed, usbstrct_c458b58d-fcfa-4082-bbcf-34e22d504ab9.xml, usbspec/UsbHighSpeed, buses.usb_device_speed, usbspec/UsbFullSpeed, usbspec/UsbSuperSpeed, UsbHighSpeed, UsbFullSpeed, _USB_DEVICE_SPEED, UsbLowSpeed, usbspec/USB_DEVICE_SPEED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usbspec.h
req.include-header: Usbspec.h
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
-	Usbspec.h
apiname:
-	USB_DEVICE_SPEED
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_SPEED
req.product: Windows 10 or later.
---

# _USB_DEVICE_SPEED enumeration


## -description


The <b>USB_DEVICE_SPEED</b> enumeration defines constants for USB device speeds. 


## -syntax


````
typedef enum  { 
  UsbLowSpeed     = 0,
  UsbFullSpeed  ,
  UsbHighSpeed  ,
  UsbSuperSpeed
} USB_DEVICE_SPEED;
````


## -enum-fields




### -field UsbLowSpeed

Indicates a low-speed USB 1.1-compliant device.


### -field UsbFullSpeed

Indicates a full-speed USB 1.1-compliant device.


### -field UsbHighSpeed

Indicates a high-speed USB 2.0-compliant device. 




### -field UsbSuperSpeed

Indicates a SuperSpeed USB 3.0-compliant device. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_DEVICE_SPEED enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

