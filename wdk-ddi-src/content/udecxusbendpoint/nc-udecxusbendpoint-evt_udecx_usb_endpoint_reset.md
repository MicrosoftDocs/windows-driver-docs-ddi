---
UID: NC:udecxusbendpoint.EVT_UDECX_USB_ENDPOINT_RESET
title: EVT_UDECX_USB_ENDPOINT_RESET (udecxusbendpoint.h)
description: The USB device emulation class extension (UdeCx) invokes this callback function to reset an endpoint of the virtual USB device.
old-location: buses\evt_udecx_usb_endpoint_reset.htm
tech.root: usbref
ms.assetid: 4220509B-A378-47F4-8E71-0290EDED89EB
ms.date: 05/07/2018
ms.keywords: EVT_UDECX_USB_ENDPOINT_RESET, EVT_UDECX_USB_ENDPOINT_RESET callback, EvtUsbEndpointReset, EvtUsbEndpointReset callback function [Buses], buses.evt_udecx_usb_endpoint_reset, udecxusbendpoint/EvtUsbEndpointReset
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
- EvtUsbEndpointReset
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UDECX_USB_ENDPOINT_RESET callback function


## -description


The USB device emulation class extension (UdeCx) invokes this callback function to reset an endpoint of the virtual USB device.


## -parameters




### -param UdecxUsbEndpoint [in]

A handle to a UDE endpoint object that represents the endpoint to reset. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627983">UdecxUsbEndpointCreate</a>.


### -param Request [in]

A handle to a framework request object that represents the request to reset the endpoint.


## -returns



This callback function does not return a value.




## -remarks



The client driver registered this callback function in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627985">UdecxUsbEndpointInitSetCallbacks</a> by supplying a function pointer to its implementation.

The reset request clears the error condition in the endpoint that causes failed I/O transfers. At that time, UdeCx can invoke the  <i>EVT_UDECX_USB_ENDPOINT_RESET</i> callback function. That call is asynchronous. The client driver completes the request and signals completion with status by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a> method .  (this is the only way the UDECX client uses the request parameter).





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh968307">How to recover from USB pipe errors</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

