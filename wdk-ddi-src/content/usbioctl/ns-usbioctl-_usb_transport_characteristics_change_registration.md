---
UID: NS:usbioctl._USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
title: _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION (usbioctl.h)
description: Contains registration information for the IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE request.
old-location: buses\usb_transport_characteristics_change_registration.htm
tech.root: usbref
ms.date: 02/25/2021
keywords: ["USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure"]
ms.keywords: "*PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure pointer [Buses], USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure [Buses], _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, buses.usb_transport_characteristics_change_registration, usbioctl/PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, usbioctl/USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION"
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
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
f1_keywords:
 - _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
 - usbioctl/_USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
 - PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
 - usbioctl/PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
 - USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
 - usbioctl/USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
 - PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
 - USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
---

# _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure

## -description

Contains registration information for the [IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE](ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change.md) request.

## -struct-fields

### -field ChangeNotificationInputFlags

A bitmask set by the client driver to register for change notifications that it is interested in. The following bits are valid:

| Value | Meaning |
| ----- | ------- |
| USB_REGISTER_FOR_TRANSPORT_LATENCY_CHANGE (0x1) | The client is notified of changes in transport latency. |
| USB_REGISTER_FOR_TRANSPORT_BANDWIDTH_CHANGE (0x2) | The client is notified of changes in bandwidth. |

### -field Handle

An opaque handle for this registration.

### -field UsbTransportCharacteristics

A [USB_TRANSPORT_CHARACTERISTICS](ns-usbioctl-_usb_transport_characteristics.md) structure that is filled by the USB driver stack with the initial values of the transport characteristics.

## -remarks

The registration handle received in this request is valid until the caller sends the [IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE](ni-usbioctl-ioctl_usb_unregister_for_transport_characteristics_change.md) request to unregister for notifications.

## -see-also

[IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE](ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change.md)
