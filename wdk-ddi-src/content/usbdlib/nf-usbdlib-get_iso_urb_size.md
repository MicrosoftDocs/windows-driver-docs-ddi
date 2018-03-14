---
UID: NF:usbdlib.GET_ISO_URB_SIZE
title: GET_ISO_URB_SIZE macro
author: windows-driver-content
description: The GET_ISO_URB_SIZE macro returns the number of bytes required to hold an isochronous transfer request.
old-location: buses\get_iso_urb_size.htm
old-project: usbref
ms.assetid: 37e96d41-3a8c-429a-a8fd-463f9be5555f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: GET_ISO_URB_SIZE, GET_ISO_URB_SIZE macro [Buses], buses.get_iso_urb_size, usbdlib/GET_ISO_URB_SIZE, usbfunc_949a4f14-4bc8-4ba1-821c-f81c6bcec0fa.xml
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbdlib.h
api_name:
-	GET_ISO_URB_SIZE
product: Windows
targetos: Windows
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




### -param n

TBD






#### - NumberOfPackets [in]

Specifies the number of isochronous transfer packets that will be part of the transfer request.


## -see-also

<a href="..\usb\ns-usb-_urb.md">URB</a>



<a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/en-us/windows/iot-core/learn-about-hardware/hardwarecompatlist">Routines for USB Client Drivers</a>



<a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a>



 

 


