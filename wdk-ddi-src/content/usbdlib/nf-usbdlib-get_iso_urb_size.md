---
UID: NF:usbdlib.GET_ISO_URB_SIZE
title: GET_ISO_URB_SIZE macro (usbdlib.h)
description: The GET_ISO_URB_SIZE macro returns the number of bytes required to hold an isochronous transfer request.
old-location: buses\get_iso_urb_size.htm
tech.root: usbref
ms.assetid: 37e96d41-3a8c-429a-a8fd-463f9be5555f
ms.date: 05/07/2018
keywords: ["GET_ISO_URB_SIZE macro"]
ms.keywords: GET_ISO_URB_SIZE, GET_ISO_URB_SIZE macro [Buses], buses.get_iso_urb_size, usbdlib/GET_ISO_URB_SIZE, usbfunc_949a4f14-4bc8-4ba1-821c-f81c6bcec0fa.xml
f1_keywords:
 - "usbdlib/GET_ISO_URB_SIZE"
req.header: usbdlib.h
req.include-header: Usbdlib.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbdlib.h
api_name:
- GET_ISO_URB_SIZE
product:
- Windows
targetos: Windows
req.typenames: 
---

# GET_ISO_URB_SIZE macro


## -description


The <b>GET_ISO_URB_SIZE</b> macro returns the number of bytes required to hold an isochronous transfer request.


## -parameters




### -param n

<p>Specifies the number of isochronous transfer packets that will be part of the transfer request.</p>



## -returns
GET_ISO_URB_SIZE returns the number of bytes required to hold an isochronous request with the given NumberOfPackets.


## -see-also




<a href="https://docs.microsoft.com/windows/iot-core/learn-about-hardware/hardwarecompatlist">Routines for USB Client Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_iso_packet_descriptor">USBD_ISO_PACKET_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_isoch_transfer">_URB_ISOCH_TRANSFER</a>
 

 

