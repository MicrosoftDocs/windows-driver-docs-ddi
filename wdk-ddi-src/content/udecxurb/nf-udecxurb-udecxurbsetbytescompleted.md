---
UID: NF:udecxurb.UdecxUrbSetBytesCompleted
title: UdecxUrbSetBytesCompleted function (udecxurb.h)
description: Sets the number of bytes transferred for the URB contained within a framework request object.
old-location: buses\udecxurbsetbytescompleted.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUrbSetBytesCompleted function"]
ms.keywords: UdecxUrbSetBytesCompleted, UdecxUrbSetBytesCompleted function [Buses], buses.udecxurbsetbytescompleted, udecxurb/UdecxUrbSetBytesCompleted
req.header: udecxurb.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UdecxUrbSetBytesCompleted
 - udecxurb/UdecxUrbSetBytesCompleted
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUrbSetBytesCompleted
---

# UdecxUrbSetBytesCompleted function


## -description

Sets the number of bytes transferred for the URB contained within a framework  request object.

## -parameters

### -param Request [in]


A handle to a framework request object that contains the <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> for the transfer.

### -param BytesCompleted

<p>The number of transferred bytes to set in the <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb"><b>URB</b></a>. This value must not be greater than the transfer buffer length.</p>

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
