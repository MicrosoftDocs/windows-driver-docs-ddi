---
UID: NS:usbioctl._USB_HUB_CAPABILITIES
title: _USB_HUB_CAPABILITIES (usbioctl.h)
description: The USB_HUB_CAPABILITIES structure has been deprecated. Use USB_HUB_CAPABILITIES_EX instead.
old-location: buses\usb_hub_capabilities.htm
tech.root: usbref
ms.assetid: a87f747f-474d-401d-9757-0820680e5c8e
ms.date: 05/07/2018
keywords: ["USB_HUB_CAPABILITIES structure"]
ms.keywords: "*PUSB_HUB_CAPABILITIES, PUSB_HUB_CAPABILITIES, PUSB_HUB_CAPABILITIES structure pointer [Buses], USB_HUB_CAPABILITIES, USB_HUB_CAPABILITIES structure [Buses], _USB_HUB_CAPABILITIES, buses.usb_hub_capabilities, usbioctl/PUSB_HUB_CAPABILITIES, usbioctl/USB_HUB_CAPABILITIES, usbstrct_b82d8bad-3ed4-40d1-a6c1-7ac416ebf157.xml"
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
req.typenames: USB_HUB_CAPABILITIES, *PUSB_HUB_CAPABILITIES
f1_keywords:
 - _USB_HUB_CAPABILITIES
 - usbioctl/_USB_HUB_CAPABILITIES
 - PUSB_HUB_CAPABILITIES
 - usbioctl/PUSB_HUB_CAPABILITIES
 - USB_HUB_CAPABILITIES
 - usbioctl/USB_HUB_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - USB_HUB_CAPABILITIES
---

# _USB_HUB_CAPABILITIES structure


## -description

The <b>USB_HUB_CAPABILITIES</b> structure has been deprecated. Use <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_capabilities_ex">USB_HUB_CAPABILITIES_EX</a> instead.

## -struct-fields

### -field HubIs2xCapable

If <b>TRUE</b>, the hub is capable of running at high speed.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_hub_capabilities">IOCTL_USB_GET_HUB_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_capabilities_ex">USB_HUB_CAPABILITIES_EX</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_cap_flags">USB_HUB_CAP_FLAGS</a>