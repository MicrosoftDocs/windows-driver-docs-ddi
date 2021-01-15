---
UID: NS:usbioctl._USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
title: _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION (usbioctl.h)
description: Contains registration information filled when the IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE request completes.
old-location: buses\usb_transport_characteristics_change_notification.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure"]
ms.keywords: "*PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure pointer [Buses], USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure [Buses], _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, buses.usb_transport_characteristics_change_notification, usbioctl/PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, usbioctl/_USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION"
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
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
f1_keywords:
 - _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
 - usbioctl/_USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
 - PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
 - usbioctl/PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
 - USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
 - usbioctl/USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
 - PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
 - USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
---

# _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure


## -description

Contains registration information filled when the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> 

request completes.

## -struct-fields

### -field Handle

An opaque handle for this registration.

### -field UsbTransportCharacteristics

A <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_transport_characteristics">USB_TRANSPORT_CHARACTERISTICS</a> structure that is filled by the USB driver stack with the initial values of the transport characteristics.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>

