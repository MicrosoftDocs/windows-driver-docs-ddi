---
UID: NC:udecxusbendpoint.EVT_UDECX_USB_ENDPOINT_START
title: EVT_UDECX_USB_ENDPOINT_START (udecxusbendpoint.h)
description: The USB device emulation class extension (UdeCx) invokes this callback function to start processing I/O requests on the specified endpoint of the virtual USB device.
old-location: buses\evt_udecx_usb_endpoint_start.htm
tech.root: usbref
ms.assetid: 3F58B6FF-65C5-4B28-81DD-3726B6695BF7
ms.date: 05/07/2018
ms.keywords: EVT_UDECX_USB_ENDPOINT_START, EVT_UDECX_USB_ENDPOINT_START callback, EvtUsbEndpointStart, EvtUsbEndpointStart callback function [Buses], buses.evt_udecx_usb_endpoint_start, udecxusbendpoint/EvtUsbEndpointStart
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- UdecxUsbEndpoint.h
api_name:
- EvtUsbEndpointStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UDECX_USB_ENDPOINT_START callback function


## -description


The USB device emulation class extension (UdeCx) invokes this callback function to start processing I/O requests on the specified endpoint of the virtual USB device.


## -parameters




### -param UdecxUsbEndpoint [in]

A handle to a UDE endpoint object that represents the endpoint which can start receiving I/O requests. The client driver retrieved this pointer in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



The client driver registered this callback function in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointinitsetcallbacks">UdecxUsbEndpointInitSetCallbacks</a> by supplying a function pointer to its implementation.

After the client driver creates an endpoint, it does not automatically start receiving I/O requests. When UdeCx is ready to forward those request for processing, it invokes the client driver's <i>EVT_UDECX_USB_ENDPOINT_START</i> function and the client driver can begin processing I/O on the endpoint’s queue, and on any queues that receive forwarded I/O for the endpoint. This callback returns the endpoint to a state of processing I/O after an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbendpoint/nc-udecxusbendpoint-evt_udecx_usb_endpoint_purge">EVT_UDECX_USB_ENDPOINT_PURGE</a> callback has and completed.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbendpoint/nc-udecxusbendpoint-evt_udecx_usb_endpoint_purge">EVT_UDECX_USB_ENDPOINT_PURGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

