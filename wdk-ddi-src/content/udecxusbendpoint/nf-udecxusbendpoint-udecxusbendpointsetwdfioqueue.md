---
UID: NF:udecxusbendpoint.UdecxUsbEndpointSetWdfIoQueue
title: UdecxUsbEndpointSetWdfIoQueue function (udecxusbendpoint.h)
description: Sets a framework queue object with a UDE endpoint.
old-location: buses\udecxusbendpointsetwdfioqueue.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUsbEndpointSetWdfIoQueue function"]
ms.keywords: UdecxUsbEndpointSetWdfIoQueue, UdecxUsbEndpointSetWdfIoQueue function [Buses], buses.udecxusbendpointsetwdfioqueue, udecxusbendpoint/UdecxUsbEndpointSetWdfIoQueue
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
 - UdecxUsbEndpointSetWdfIoQueue
 - udecxusbendpoint/UdecxUsbEndpointSetWdfIoQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbEndpointSetWdfIoQueue
---

# UdecxUsbEndpointSetWdfIoQueue function


## -description

Sets a framework queue object with a UDE endpoint.

## -parameters

### -param UdecxUsbEndpoint 

[in]
A handle to a UDE endpoint object. The client driver retrieved this pointer in the previous call to <a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>.

### -param WdfQueue 

[in]
A handle to a framework queue object that will handle requests sent to the endpoint. The client driver retrieved this pointer in the previous call to <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
