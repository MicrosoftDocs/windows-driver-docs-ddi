---
UID: NF:udecxusbendpoint.UdecxUsbEndpointInitSetCallbacks
title: UdecxUsbEndpointInitSetCallbacks function (udecxusbendpoint.h)
description: Sets pointers to UDE client driver-implemented callback functions in the initialization parameters of the simple endpoint to create.
old-location: buses\udecxusbendpointinitsetcallbacks.htm
tech.root: usbref
ms.assetid: 0F6EBBDA-FA0B-4044-905B-535D4FFEC5D2
ms.date: 05/07/2018
ms.keywords: UdecxUsbEndpointInitSetCallbacks, UdecxUsbEndpointInitSetCallbacks function [Buses], buses.udecxusbendpointinitsetcallbacks, udecxusbendpoint/UdecxUsbEndpointInitSetCallbacks
ms.topic: function
f1_keywords:
 - "udecxusbendpoint/UdecxUsbEndpointInitSetCallbacks"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxUsbEndpointInitSetCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbEndpointInitSetCallbacks function


## -description


Sets pointers to UDE client driver-implemented  callback functions in the initialization parameters of the simple endpoint to create.


## -parameters




### -param UdecxUsbEndpointInit

<p>A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbendpoint/nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate"><b>UdecxUsbSimpleEndpointInitAllocate</b></a>.</p>


### -param EndpointCallbacks [in]

A pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbendpoint/ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks">UDECX_USB_ENDPOINT_CALLBACKS</a> that contains function pointers to event callback functions implemented by the UDE client driver. 


## -returns



This function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

