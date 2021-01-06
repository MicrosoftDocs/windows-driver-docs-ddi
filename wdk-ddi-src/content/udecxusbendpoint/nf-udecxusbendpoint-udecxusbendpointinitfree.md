---
UID: NF:udecxusbendpoint.UdecxUsbEndpointInitFree
title: UdecxUsbEndpointInitFree function (udecxusbendpoint.h)
description: Release the resources that were allocated by the UdecxUsbSimpleEndpointInitAllocate call.
old-location: buses\udecxusbendpointinitfree.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUsbEndpointInitFree function"]
ms.keywords: UdecxUsbEndpointInitFree, UdecxUsbEndpointInitFree function [Buses], buses.udecxusbendpointinitfree, udecxusbendpoint/UdecxUsbEndpointInitFree
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
 - UdecxUsbEndpointInitFree
 - udecxusbendpoint/UdecxUsbEndpointInitFree
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbEndpointInitFree
---

# UdecxUsbEndpointInitFree function


## -description

Release the resources that were allocated by the  <a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate">UdecxUsbSimpleEndpointInitAllocate</a> call.

## -parameters

### -param Init 

[in]
A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate">UdecxUsbSimpleEndpointInitAllocate</a>.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
