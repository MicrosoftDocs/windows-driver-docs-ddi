---
UID: NF:udecxusbendpoint.UdecxUsbEndpointPurgeComplete
title: UdecxUsbEndpointPurgeComplete function (udecxusbendpoint.h)
description: Completes an asynchronous request for canceling all I/O requests queued to the specified endpoint.
old-location: buses\udecxusbendpointpurgecomplete.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUsbEndpointPurgeComplete function"]
ms.keywords: UdecxUsbEndpointPurgeComplete, UdecxUsbEndpointPurgeComplete function [Buses], buses.udecxusbendpointpurgecomplete, udecxusbendpoint/UdecxUsbEndpointPurgeComplete
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
 - UdecxUsbEndpointPurgeComplete
 - udecxusbendpoint/UdecxUsbEndpointPurgeComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbEndpointPurgeComplete
---

# UdecxUsbEndpointPurgeComplete function


## -description

Completes an asynchronous request for canceling all I/O requests queued to the specified endpoint.

## -parameters

### -param UdecxUsbEndpoint [in]


A handle to a UDE endpoint object. The client driver retrieved this pointer in the previous call to <a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nc-udecxusbendpoint-evt_udecx_usb_endpoint_purge">EVT_UDECX_USB_ENDPOINT_PURGE</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
