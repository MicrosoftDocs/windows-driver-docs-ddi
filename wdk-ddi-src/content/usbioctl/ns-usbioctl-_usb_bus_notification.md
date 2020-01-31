---
UID: NS:usbioctl._USB_BUS_NOTIFICATION
title: _USB_BUS_NOTIFICATION (usbioctl.h)
description: 
ms.assetid: c6982976-fd7f-4be2-9c2f-f7e2fb8a6260
ms.date: 10/19/2018
f1_keywords:
 - "usbioctl/_USB_BUS_NOTIFICATION"
ms.keywords: _USB_BUS_NOTIFICATION, USB_BUS_NOTIFICATION, *PUSB_BUS_NOTIFICATION, 
req.header: usbioctl.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: USB_BUS_NOTIFICATION, *PUSB_BUS_NOTIFICATION
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbioctl.h
api_name: 
- _USB_BUS_NOTIFICATION
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _USB_BUS_NOTIFICATION structure

## -description
Stores certain bus information. This structure is used in the [IOCTL_INTERNAL_USB_GET_BUS_INFO](ni-usbioctl-ioctl_internal_usb_get_bus_info.md) request.

## -struct-fields

### -field NotificationType
A [**USB_NOTIFICATION_TYPE**](ne-usbioctl-_usb_notification_type.md)-value that indicates the type of notification.

### -field TotalBandwidth
The total bandwidth, in bits per second, available on the bus.
 
### -field ConsumedBandwidth
The mean bandwidth already in use, in bits per second.
 
### -field ControllerNameLength
The length of the Unicode symbolic name (in bytes) for the host controller to which this device is attached. The length does not include NULL.

## -remarks

## -see-also
