---
UID: NC:udecxusbendpoint.EVT_UDECX_USB_ENDPOINT_START
title: EVT_UDECX_USB_ENDPOINT_START
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function to start processing I/O requests on the specified endpoint of the virtual USB device.
old-location: buses\evt_udecx_usb_endpoint_start.htm
old-project: usbref
ms.assetid: 3F58B6FF-65C5-4B28-81DD-3726B6695BF7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UDECX_USB_ENDPOINT_START, EvtUsbEndpointStart, EvtUsbEndpointStart callback function [Buses], buses.evt_udecx_usb_endpoint_start, udecxusbendpoint/EvtUsbEndpointStart
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	UdecxUsbEndpoint.h
api_name:
-	EvtUsbEndpointStart
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---

# EVT_UDECX_USB_ENDPOINT_START callback


## -description


The USB device emulation class extension (UdeCx) invokes this callback function to start processing I/O requests on the specified endpoint of the virtual USB device.


## -prototype


````
EVT_UDECX_USB_ENDPOINT_START EvtUsbEndpointStart;

void EvtUsbEndpointStart(
  _In_ UDECXUSBENDPOINT UdecxUsbEndpoint
)
{ ... }
````


## -parameters




### -param UdecxUsbEndpoint [in]

A handle to a UDE endpoint object that represents the endpoint which can start receiving I/O requests. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



The client driver registered this callback function in a previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointinitsetcallbacks.md">UdecxUsbEndpointInitSetCallbacks</a> by supplying a function pointer to its implementation.

After the client driver creates an endpoint, it does not automatically start receiving I/O requests. When UdeCx is ready to forward those request for processing, it invokes the client driver's <i>EVT_UDECX_USB_ENDPOINT_START</i> function and the client driver can begin processing I/O on the endpoint’s queue, and on any queues that receive forwarded I/O for the endpoint. This callback returns the endpoint to a state of processing I/O after an <a href="..\udecxusbendpoint\nc-udecxusbendpoint-evt_udecx_usb_endpoint_purge.md">EVT_UDECX_USB_ENDPOINT_PURGE</a> callback has and completed.





## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="..\udecxusbendpoint\nc-udecxusbendpoint-evt_udecx_usb_endpoint_purge.md">EVT_UDECX_USB_ENDPOINT_PURGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UDECX_USB_ENDPOINT_START callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

