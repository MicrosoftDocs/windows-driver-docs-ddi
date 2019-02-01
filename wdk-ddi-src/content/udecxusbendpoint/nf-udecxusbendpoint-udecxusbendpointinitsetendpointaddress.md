---
UID: NF:udecxusbendpoint.UdecxUsbEndpointInitSetEndpointAddress
title: UdecxUsbEndpointInitSetEndpointAddress function (udecxusbendpoint.h)
description: Sets the address of the endpoint in the initialization parameters of the simple endpoint to create.
old-location: buses\udecxusbendpointinitsetendpointaddress.htm
tech.root: usbref
ms.assetid: 1C6DDEAE-5E49-40AF-9667-3C185A82BDE8
ms.date: 05/07/2018
ms.keywords: UdecxUsbEndpointInitSetEndpointAddress, UdecxUsbEndpointInitSetEndpointAddress function [Buses], buses.udecxusbendpointinitsetendpointaddress, udecxusbendpoint/UdecxUsbEndpointInitSetEndpointAddress
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUsbEndpointInitSetEndpointAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbEndpointInitSetEndpointAddress function


## -description


Sets the address of the endpoint in the initialization parameters of the simple endpoint to create.


## -parameters




### -param Init [in, out]

A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627989">UdecxUsbSimpleEndpointInitAllocate</a>.


### -param EndpointAddress [in]

Specifies the USB-defined endpoint address. The four low-order bits specify the endpoint number. The high-order bit specifies the direction of data flow on this endpoint: 1 for in, 0 for out.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627983">UdecxUsbEndpointCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

