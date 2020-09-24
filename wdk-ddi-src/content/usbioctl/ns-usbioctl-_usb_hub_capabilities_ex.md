---
UID: NS:usbioctl._USB_HUB_CAPABILITIES_EX
title: _USB_HUB_CAPABILITIES_EX (usbioctl.h)
description: The USB_HUB_CAPABILITIES_EX structure is used with the IOCTL_USB_GET_HUB_CAPABILITIES I/O control request to retrieve the capabilities of a particular USB hub.
old-location: buses\usb_hub_capabilities_ex.htm
tech.root: usbref
ms.assetid: deb8d710-6137-4f69-8fde-00d46cdb6f4f
ms.date: 05/07/2018
keywords: ["USB_HUB_CAPABILITIES_EX structure"]
ms.keywords: "*PUSB_HUB_CAPABILITIES_EX, PUSB_HUB_CAPABILITIES_EX, PUSB_HUB_CAPABILITIES_EX structure pointer [Buses], USB_HUB_CAPABILITIES_EX, USB_HUB_CAPABILITIES_EX structure [Buses], _USB_HUB_CAPABILITIES_EX, buses.usb_hub_capabilities_ex, usbioctl/PUSB_HUB_CAPABILITIES_EX, usbioctl/USB_HUB_CAPABILITIES_EX, usbstrct_42446556-393a-4d58-934e-f63d62fa3c07.xml"
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
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
req.typenames: USB_HUB_CAPABILITIES_EX, *PUSB_HUB_CAPABILITIES_EX
f1_keywords:
 - _USB_HUB_CAPABILITIES_EX
 - usbioctl/_USB_HUB_CAPABILITIES_EX
 - PUSB_HUB_CAPABILITIES_EX
 - usbioctl/PUSB_HUB_CAPABILITIES_EX
 - USB_HUB_CAPABILITIES_EX
 - usbioctl/USB_HUB_CAPABILITIES_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - USB_HUB_CAPABILITIES_EX
---

# _USB_HUB_CAPABILITIES_EX structure


## -description

The <b>USB_HUB_CAPABILITIES_EX</b> structure is used with the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_hub_capabilities">IOCTL_USB_GET_HUB_CAPABILITIES</a> I/O control request to retrieve the capabilities of a particular USB hub.

## -struct-fields

### -field CapabilityFlags

A <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_cap_flags">USB_HUB_CAP_FLAGS</a> structure that reports the hub capabilities.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_hub_capabilities">IOCTL_USB_GET_HUB_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_cap_flags">USB_HUB_CAP_FLAGS</a>