---
UID: NS:usb._USBD_STREAM_INFORMATION
title: _USBD_STREAM_INFORMATION (usb.h)
description: The USBD_STREAM_INFORMATION structure stores information about a stream associated with a bulk endpoint.
old-location: buses\usbd_stream_information.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBD_STREAM_INFORMATION structure"]
ms.keywords: "*PUSBD_STREAM_INFORMATION, PUSBD_STREAM_INFORMATION, PUSBD_STREAM_INFORMATION structure pointer [Buses], USBD_STREAM_INFORMATION, USBD_STREAM_INFORMATION structure [Buses], _USBD_STREAM_INFORMATION, buses.usbd_stream_information, usb/PUSBD_STREAM_INFORMATION, usb/USBD_STREAM_INFORMATION"
req.header: usb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.typenames: USBD_STREAM_INFORMATION, *PUSBD_STREAM_INFORMATION
f1_keywords:
 - _USBD_STREAM_INFORMATION
 - usb/_USBD_STREAM_INFORMATION
 - PUSBD_STREAM_INFORMATION
 - usb/PUSBD_STREAM_INFORMATION
 - USBD_STREAM_INFORMATION
 - usb/USBD_STREAM_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usb.h
api_name:
 - _USBD_STREAM_INFORMATION
 - PUSBD_STREAM_INFORMATION
 - USBD_STREAM_INFORMATION
---

# _USBD_STREAM_INFORMATION structure


## -description

The <b>USBD_STREAM_INFORMATION</b> structure stores information about a stream associated with a bulk endpoint.

## -struct-fields

### -field PipeHandle

An opaque handle to  the stream.

### -field StreamID

Stream identifier. The open-static streams request obtains stream identifiers that are assigned by the USB driver stack.

### -field MaximumTransferSize

Maximum transfer size (in bytes) that a client driver can send in a single URB for an I/O transfer to the stream.

### -field PipeFlags

Reserved. Do not use.

## -remarks

A client driver allocates an array of  <b>USBD_STREAM_INFORMATION</b> structures and sends it in an open-streams request (URB_FUNCTION_OPEN_STATIC_STREAMS).  Upon completion, the USB driver stack retrieves stream information and populates each <b>USBD_STREAM_INFORMATION</b> structure with stream information.  The stream identifiers returned by the request are sequential and start at 1.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">How to Open and Close Static Streams in a USB Bulk Endpoint</a>



<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="/windows-hardware/drivers/ddi/_usbref/#structures">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a>



<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb_open_static_streams">_URB_OPEN_STATIC_STREAMS</a>

