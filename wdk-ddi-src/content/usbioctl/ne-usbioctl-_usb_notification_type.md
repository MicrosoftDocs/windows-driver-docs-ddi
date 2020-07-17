---
UID: NE:usbioctl._USB_NOTIFICATION_TYPE
title: _USB_NOTIFICATION_TYPE (usbioctl.h)
description: 
ms.assetid: cb5eaa01-dec9-4028-b0b1-7a1f240c02ae
ms.date: 10/19/2018
keywords: ["_USB_NOTIFICATION_TYPE enumeration"]
f1_keywords:
 - "usbioctl/_USB_NOTIFICATION_TYPE"
 - "_USB_NOTIFICATION_TYPE"
ms.keywords: _USB_NOTIFICATION_TYPE, USB_NOTIFICATION_TYPE, 
req.header: usbioctl.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: USB_NOTIFICATION_TYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbioctl.h
api_name: 
- _USB_NOTIFICATION_TYPE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _USB_NOTIFICATION_TYPE enumeration

## -description
Defines values for the type of notification that can be requested by a client driver.

## -enum-fields

### -field EnumerationFailure
Reserved.

### -field InsufficentBandwidth
Reserved.

### -field InsufficentPower
Reserved.
### -field OverCurrent
Reserved.
### -field ResetOvercurrent
Reserved.
### -field AcquireBusInfo
Indicates the information about the bus. This is retrieved by the [IOCTL_INTERNAL_USB_GET_BUS_INFO](ni-usbioctl-ioctl_internal_usb_get_bus_info.md) request. Also see, [**USB_BUS_NOTIFICATION**](ns-usbioctl-_usb_bus_notification.md).

### -field AcquireHubName
Reserved.
### -field AcquireControllerName
Reserved.
### -field HubOvercurrent
Reserved.
### -field HubPowerChange
Reserved.
### -field HubNestedTooDeeply
Reserved.
### -field ModernDeviceInLegacyHub
Reserved.
## -remarks

## -see-also
