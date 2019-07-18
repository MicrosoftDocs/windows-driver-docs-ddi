---
UID: NS:usbioctl._USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
title: _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION (usbioctl.h)
description: Contains registration information filled when the IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE request completes.
old-location: buses\usb_transport_characteristics_change_notification.htm
tech.root: usbref
ms.assetid: C7E1996F-E00C-4A89-8CE4-E9B4987AEED1
ms.date: 05/07/2018
ms.keywords: "*PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure pointer [Buses], USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure [Buses], _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, buses.usb_transport_characteristics_change_notification, usbioctl/PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, usbioctl/_USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION"
ms.topic: struct
f1_keywords:
 - "usbioctl/USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
---

# _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure


## -description


Contains registration information filled when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> 

request completes.


## -struct-fields




### -field Handle

An opaque handle for this registration.


### -field UsbTransportCharacteristics

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ns-usbioctl-_usb_transport_characteristics">USB_TRANSPORT_CHARACTERISTICS</a> structure that is filled by the USB driver stack with the initial values of the transport characteristics. 



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>
 

 

