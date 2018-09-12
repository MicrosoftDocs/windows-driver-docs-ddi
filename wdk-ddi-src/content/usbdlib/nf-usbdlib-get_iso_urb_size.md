---
UID: NF:usbdlib.GET_ISO_URB_SIZE
title: GET_ISO_URB_SIZE macro
author: windows-driver-content
description: The GET_ISO_URB_SIZE macro returns the number of bytes required to hold an isochronous transfer request.
old-location: buses\get_iso_urb_size.htm
tech.root: usbref
ms.assetid: 37e96d41-3a8c-429a-a8fd-463f9be5555f
ms.author: windowsdriverdev
ms.date: 5/7/2018
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






#### - NumberOfPackets [in]

Specifies the number of isochronous transfer packets that will be part of the transfer request.


## -see-also




<a href="https://docs.microsoft.com/en-us/windows/iot-core/learn-about-hardware/hardwarecompatlist">Routines for USB Client Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539084">USBD_ISO_PACKET_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540414">_URB_ISOCH_TRANSFER</a>
 

 

