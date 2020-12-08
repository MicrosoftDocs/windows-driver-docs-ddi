---
UID: NS:usbspec._USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
title: _USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR (usbspec.h)
description: The USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR structure is used by USB client drivers to retrieve a USB-defined SuperSpeed Endpoint Companion descriptor. For more information, see section 9.6.7 and Table 9-20 in the official USB 3.0 specification.
old-location: buses\usb_superspeed_endpoint_companion_descriptor.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR structure"]
ms.keywords: "*PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR structure pointer [Buses], USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR structure [Buses], _USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, buses.usb_superspeed_endpoint_companion_descriptor, usbspec/PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, usbspec/USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR"
req.header: usbspec.h
req.include-header: Usbspec.h
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
req.typenames: USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
f1_keywords:
 - _USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
 - usbspec/_USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
 - PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
 - usbspec/PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
 - USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
 - usbspec/USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbspec.h
api_name:
 - USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
---

# _USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR structure


## -description

The <b>USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</b> structure is used by USB client drivers to retrieve a USB-defined SuperSpeed Endpoint Companion descriptor.

The members of this structure are described in the Universal Serial Bus 3.1 Specification available at [USB Document Library](https://www.usb.org/documents). See section 9.6.7.

## -struct-fields

### -field bLength

Specifies the length, in bytes, of this descriptor.

### -field bDescriptorType

Specifies the descriptor type. Must be set to USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR.

### -field bMaxBurst

Specifies the maximum number of packets that the endpoint can send or receive as a part of a burst.

### -field bmAttributes

### -field bmAttributes.AsUchar

Specifies the length of the structures.

### -field bmAttributes.Bulk

### -field bmAttributes.Bulk.MaxStreams

Specifies the maximum number of streams supported by the bulk endpoint.

### -field bmAttributes.Bulk.Reserved1

Reserved. Do not use.

### -field bmAttributes.Isochronous

### -field bmAttributes.Isochronous.Mult

Specifies a zero-based number that determines the maximum number of packets (bMaxBurst *  (Mult + 1)) that can be sent to the endpoint within a service interval.

### -field bmAttributes.Isochronous.Reserved2

Reserved. Do not use.

### -field bmAttributes.Isochronous.SspCompanion

### -field wBytesPerInterval

Number of bytes per interval.

## -remarks

A client driver that supports streams associated with a bulk endpoint, uses <b>USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</b> to get the maximum number of streams supported by the endpoint. That information is required by the client driver in an open-streams request. In the request, the specified value for <b>NumberOfStreams</b> member of the <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb_open_static_streams">_URB_OPEN_STATIC_STREAMS</a> structure cannot exceed the <b>MaxStreams</b> value reported in <b>USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</b>. For more information about opening streams, see <a href="/windows-hardware/drivers/ddi/index">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">USB Structures</a>
