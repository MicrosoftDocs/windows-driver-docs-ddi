---
UID: NF:udecxusbendpoint.UdecxUsbEndpointInitSetEndpointAddress
title: UdecxUsbEndpointInitSetEndpointAddress function (udecxusbendpoint.h)
description: Sets the address of the endpoint in the initialization parameters of the simple endpoint to create.
old-location: buses\udecxusbendpointinitsetendpointaddress.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUsbEndpointInitSetEndpointAddress function"]
ms.keywords: UdecxUsbEndpointInitSetEndpointAddress, UdecxUsbEndpointInitSetEndpointAddress function [Buses], buses.udecxusbendpointinitsetendpointaddress, udecxusbendpoint/UdecxUsbEndpointInitSetEndpointAddress
req.header: udecxusbendpoint.h
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
 - UdecxUsbEndpointInitSetEndpointAddress
 - udecxusbendpoint/UdecxUsbEndpointInitSetEndpointAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbEndpointInitSetEndpointAddress
---

# UdecxUsbEndpointInitSetEndpointAddress function


## -description

Sets the address of the endpoint in the initialization parameters of the simple endpoint to create.

## -parameters

### -param Init 

[in, out]
A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate">UdecxUsbSimpleEndpointInitAllocate</a>.

### -param EndpointAddress 

[in]
Specifies the USB-defined endpoint address. The four low-order bits specify the endpoint number. The high-order bit specifies the direction of data flow on this endpoint: 1 for in, 0 for out.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
