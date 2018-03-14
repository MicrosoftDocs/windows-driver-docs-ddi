---
UID: NS:usbioctl._USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION
title: "_USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION"
author: windows-driver-content
description: Contains unregistration information for the IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE request.
old-location: buses\usb_transport_characteristics_change_unregistration.htm
old-project: usbref
ms.assetid: 22F185EB-103D-4D7D-94B7-D34D48B1C526
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION structure pointer [Buses], USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION structure [Buses], _USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, buses.usb_transport_characteristics_change_unregistration, usbioctl/PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, usbioctl/USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: 
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
-	Usbioctl.h
api_name:
-	USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION
product: Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION
req.product: Windows 10 or later.
---

# _USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION structure


## -description


Contains unregistration information for the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_unregister_for_transport_characteristics_change.md">IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> 

request.


## -syntax


````
typedef struct _USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION {
  USB_CHANGE_REGISTRATION_HANDLE  Handle;
} USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION;
````


## -struct-fields




### -field Handle

An opaque handle for registration that the client driver obtained in the previous <a href="..\usbioctl\ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change.md">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> request.


## -see-also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_unregister_for_transport_characteristics_change.md">IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>



 

 


