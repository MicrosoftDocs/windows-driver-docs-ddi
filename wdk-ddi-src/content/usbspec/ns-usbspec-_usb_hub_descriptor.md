---
UID: NS:usbspec._USB_HUB_DESCRIPTOR
title: _USB_HUB_DESCRIPTOR (usbspec.h)
description: The USB_HUB_DESCRIPTOR structure contains a hub descriptor.
old-location: buses\usb_hub_descriptor.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USB_HUB_DESCRIPTOR structure"]
ms.keywords: "*PUSB_HUB_DESCRIPTOR, PUSB_HUB_DESCRIPTOR, PUSB_HUB_DESCRIPTOR structure pointer [Buses], USB_HUB_DESCRIPTOR, USB_HUB_DESCRIPTOR structure [Buses], _USB_HUB_DESCRIPTOR, buses.usb_hub_descriptor, usbspec/PUSB_HUB_DESCRIPTOR, usbspec/USB_HUB_DESCRIPTOR, usbstrct_b21769d6-aab1-43b9-8d48-bde249f5c325.xml"
req.header: usbspec.h
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
req.typenames: USB_HUB_DESCRIPTOR, *PUSB_HUB_DESCRIPTOR
f1_keywords:
 - _USB_HUB_DESCRIPTOR
 - usbspec/_USB_HUB_DESCRIPTOR
 - PUSB_HUB_DESCRIPTOR
 - usbspec/PUSB_HUB_DESCRIPTOR
 - USB_HUB_DESCRIPTOR
 - usbspec/USB_HUB_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbspec.h
api_name:
 - USB_HUB_DESCRIPTOR
---

# _USB_HUB_DESCRIPTOR structure


## -description

The <b>USB_HUB_DESCRIPTOR</b> structure contains a hub descriptor.
The members of this structure are described in the Universal Serial Bus 3.1 Specification available at [USB Document Library](https://www.usb.org/documents). See section 10.15.2.1.

## -struct-fields

### -field bDescriptorLength

The length, in bytes, of the descriptor.

### -field bDescriptorType

The descriptor type. For hub descriptors, this value should be 0x29.

### -field bNumberOfPorts

The number of ports on the hub.

### -field wHubCharacteristics

The hub characteristics. For more information about this member, see Universal Serial Bus Specification.

### -field bPowerOnToPowerGood

The time, in 2-millisecond intervals, that it takes the device to turn on completely. For more information about this member, see Universal Serial Bus Specification.

### -field bHubControlCurrent

The maximum current requirements, in milliamperes, of the controller component of the hub.

### -field bRemoveAndPowerMask

Not currently implemented. Do not use this member. 

This member implements DeviceRemovable and PortPwrCtrlMask fields of the hub descriptor. For more information about these fields, see Universal Serial Bus Specification.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information">USB_HUB_INFORMATION</a>
