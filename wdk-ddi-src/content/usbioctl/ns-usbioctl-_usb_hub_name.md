---
UID: NS:usbioctl._USB_HUB_NAME
title: _USB_HUB_NAME (usbioctl.h)
description: The USB_HUB_NAME structure stores the hub's symbolic device name.
old-location: buses\usb_hub_name.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USB_HUB_NAME structure"]
ms.keywords: "*PUSB_HUB_NAME, PUSB_HUB_NAME, PUSB_HUB_NAME structure pointer [Buses], USB_HUB_NAME, USB_HUB_NAME structure [Buses], _USB_HUB_NAME, buses.usb_hub_name, usbioctl/PUSB_HUB_NAME, usbioctl/USB_HUB_NAME, usbstrct_d20b3e12-7b5c-408d-929e-2d781a765f56.xml"
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
targetos: Windows
req.typenames: USB_HUB_NAME, *PUSB_HUB_NAME
f1_keywords:
 - _USB_HUB_NAME
 - usbioctl/_USB_HUB_NAME
 - PUSB_HUB_NAME
 - usbioctl/PUSB_HUB_NAME
 - USB_HUB_NAME
 - usbioctl/USB_HUB_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - USB_HUB_NAME
---

# _USB_HUB_NAME structure


## -description

The <b>USB_HUB_NAME</b> structure stores the hub's symbolic device name.

## -struct-fields

### -field ActualLength

The size of the Unicode string pointed to by <b>HubName</b>.  The <b>ActualLength</b> value indicates the length of the string and not the entire structure.

### -field HubName

A NULL-terminated Unicode string that contains the hub's symbolic device name.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_get_controller_name">IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME</a>



<a href="/windows-hardware/drivers/ddi/index">USB Structures</a>
