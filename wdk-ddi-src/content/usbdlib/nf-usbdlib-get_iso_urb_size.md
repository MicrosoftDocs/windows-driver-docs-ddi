---
UID: NF:usbdlib.GET_ISO_URB_SIZE
title: GET_ISO_URB_SIZE macro
author: windows-driver-content
description: The GET_ISO_URB_SIZE macro returns the number of bytes required to hold an isochronous transfer request.
old-location: buses\get_iso_urb_size.htm
old-project: usbref
ms.assetid: 37e96d41-3a8c-429a-a8fd-463f9be5555f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: GET_ISO_URB_SIZE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GET_ISO_URB_SIZE
req.alt-loc: usbdlib.h
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
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# GET_ISO_URB_SIZE macro



## -description
The <b>GET_ISO_URB_SIZE</b> macro returns the number of bytes required to hold an isochronous transfer request.



## -syntax

````
ULONG  GET_ISO_URB_SIZE(
  [in] ULONG   NumberOfPackets
);
````


## -parameters

### -param NumberOfPackets [in]

Specifies the number of isochronous transfer packets that will be part of the transfer request.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\usb\ns-usb-_urb.md">URB</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a>
</dt>
<dt><a href="usb_interfaces.htm#client">Routines for USB Client Drivers</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20GET_ISO_URB_SIZE macro%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

