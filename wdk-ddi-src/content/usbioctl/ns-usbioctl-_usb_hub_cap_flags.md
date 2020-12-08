---
UID: NS:usbioctl._USB_HUB_CAP_FLAGS
title: _USB_HUB_CAP_FLAGS (usbioctl.h)
description: The USB_HUB_CAP_FLAGS structure is used to report the capabilities of a hub.
old-location: buses\usb_hub_cap_flags.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USB_HUB_CAP_FLAGS structure"]
ms.keywords: "*PUSB_HUB_CAP_FLAGS, PUSB_HUB_CAP_FLAGS, PUSB_HUB_CAP_FLAGS union pointer [Buses], USB_HUB_CAP_FLAGS, USB_HUB_CAP_FLAGS union [Buses], _USB_HUB_CAP_FLAGS, buses.usb_hub_cap_flags, usbioctl/PUSB_HUB_CAP_FLAGS, usbioctl/USB_HUB_CAP_FLAGS, usbstrct_0c0ca119-db83-4486-9b65-f16c70716c14.xml"
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
req.typenames: USB_HUB_CAP_FLAGS, *PUSB_HUB_CAP_FLAGS
f1_keywords:
 - _USB_HUB_CAP_FLAGS
 - usbioctl/_USB_HUB_CAP_FLAGS
 - PUSB_HUB_CAP_FLAGS
 - usbioctl/PUSB_HUB_CAP_FLAGS
 - USB_HUB_CAP_FLAGS
 - usbioctl/USB_HUB_CAP_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - USB_HUB_CAP_FLAGS
---

# _USB_HUB_CAP_FLAGS structure


## -description

The <b>USB_HUB_CAP_FLAGS</b> structure is used to report the capabilities of a hub.

## -struct-fields

### -field ul

A bitmask that represents the hub capabilities.

### -field HubIsHighSpeedCapable

If <b>TRUE</b>, the hub is high speed-capable. This capability does not necessarily mean that the hub is operating at high speed

### -field HubIsHighSpeed

If <b>TRUE</b>, the hub is high speed.

### -field HubIsMultiTtCapable

If <b>TRUE</b>, the hub is capable of doing multiple transaction translations simultaneously.

### -field HubIsMultiTt

If <b>TRUE</b>, the hub is configured to perform multiple transaction translations simultaneously.

### -field HubIsRoot

If <b>TRUE</b>, the hub is the root hub.

### -field HubIsArmedWakeOnConnect

If <b>TRUE</b>, the hub is armed to wake when a device is connected to the hub.

### -field HubIsBusPowered

A boolean value that indicates whether the hub is bus-powered. <b>TRUE</b>, the hub is bus-powered; <b>FALSE</b>, the hub is self-powered.

### -field ReservedMBZ

Reserved. Do not use.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_capabilities_ex">USB_HUB_CAPABILITIES_EX</a>
