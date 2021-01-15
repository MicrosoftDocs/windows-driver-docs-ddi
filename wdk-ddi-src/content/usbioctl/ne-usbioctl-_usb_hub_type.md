---
UID: NE:usbioctl._USB_HUB_TYPE
title: _USB_HUB_TYPE (usbioctl.h)
description: The USB_HUB_TYPE enumeration defines constants that indicate the type of USB hub. The hub type is retrieved by the IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request.
old-location: buses\usb_hub_type.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USB_HUB_TYPE enumeration"]
ms.keywords: USB_HUB_TYPE, USB_HUB_TYPE enumeration [Buses], Usb20Hub, Usb30Hub, UsbRootHub, _USB_HUB_TYPE, buses.usb_hub_type, usbioctl/USB_HUB_TYPE, usbioctl/Usb20Hub, usbioctl/Usb30Hub, usbioctl/UsbRootHub
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
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
req.typenames: USB_HUB_TYPE
f1_keywords:
 - _USB_HUB_TYPE
 - usbioctl/_USB_HUB_TYPE
 - USB_HUB_TYPE
 - usbioctl/USB_HUB_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - _USB_HUB_TYPE
 - USB_HUB_TYPE
---

# _USB_HUB_TYPE enumeration


## -description

The <b>USB_HUB_TYPE</b> enumeration defines constants that indicate the type of USB hub.

The hub type is retrieved by the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_hub_information_ex">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request.

The request retrieves the hub descriptor associated with the specified hub in the <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information_ex">USB_HUB_INFORMATION_EX</a> structure. The   <b>HubType</b> member contains a <b>USB_HUB_TYPE</b> enumerator that the application can use to evaluate the type of hub descriptor retrieved by the request.

## -enum-fields

### -field UsbRootHub

Indicates a root hub.

### -field Usb20Hub

Indicates that the retrieved hub descriptor is defined in USB 2.0 and 1.1 specifications.

### -field Usb30Hub

Indicates that the retrieved hub descriptor is defined in USB 3.0 specification.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_hub_information_ex">IOCTL_USB_GET_HUB_INFORMATION_EX</a>



<a href="/windows-hardware/drivers/ddi/_usbref/#enumerations">USB Constants and Enumerations</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information_ex">USB_HUB_INFORMATION_EX</a>

