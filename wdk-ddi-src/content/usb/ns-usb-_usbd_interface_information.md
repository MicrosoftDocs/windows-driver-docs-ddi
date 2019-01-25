---
UID: NS:usb._USBD_INTERFACE_INFORMATION
title: "_USBD_INTERFACE_INFORMATION" (usb.h)
description: The USBD_INTERFACE_INFORMATION structure holds information about an interface for a configuration on a USB device.
old-location: buses\usbd_interface_information.htm
tech.root: usbref
ms.assetid: dde09937-14fb-423b-8905-8a398a9c5902
ms.date: 05/07/2018
ms.keywords: "*PUSBD_INTERFACE_INFORMATION, PUSBD_INTERFACE_INFORMATION, PUSBD_INTERFACE_INFORMATION structure pointer [Buses], USBD_INTERFACE_INFORMATION, USBD_INTERFACE_INFORMATION structure [Buses], _USBD_INTERFACE_INFORMATION, buses.usbd_interface_information, usb/PUSBD_INTERFACE_INFORMATION, usb/USBD_INTERFACE_INFORMATION, usbstrct_1d2a2627-f530-4ccb-8473-0f028ab44acc.xml"
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
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
-	usb.h
api_name:
-	USBD_INTERFACE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: USBD_INTERFACE_INFORMATION, *PUSBD_INTERFACE_INFORMATION
---

# _USBD_INTERFACE_INFORMATION structure


## -description


The <b>USBD_INTERFACE_INFORMATION</b> structure holds information about an interface for a configuration on a USB device.


## -struct-fields




### -field Length

Specifies the length, in bytes, of this structure.


### -field InterfaceNumber

Specifies the device-defined index identifier for this interface.


### -field AlternateSetting

Specifies a device-defined index identifier that indicates which alternate setting this interface is using, should use, or describes.


### -field Class

Contains a USB-assigned identifier that specifies a USB-defined class that this interface conforms to.


### -field SubClass

Contains a USB-assigned identifier that specifies a USB-defined subclass that this interface conforms to. This code is specific to the code in <b>Class</b>.


### -field Protocol

Contains a USB-assigned identifier that specifies a USB-defined protocol that this interface conforms to. This code is specific to the codes in <b>Class</b> and <b>SubClass</b>.


### -field Reserved

Reserved.


### -field InterfaceHandle

Contains a host controller driver-defined handle that is used to access this interface. This member should be treated as opaque.


### -field NumberOfPipes

Specifies the number of pipes (endpoints) in this interface.


### -field Pipes

Pointer to the first element in the array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539114">USBD_PIPE_INFORMATION</a> structures. The length of the array depends on the number of endpoints in the interface descriptor.


## -remarks



Members that are part of this structure, but not described here, should be treated as opaque and considered to be reserved for system use.

The reserved members of this structure must be treated as opaque and are reserved for system use.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539114">USBD_PIPE_INFORMATION</a>
 

 

