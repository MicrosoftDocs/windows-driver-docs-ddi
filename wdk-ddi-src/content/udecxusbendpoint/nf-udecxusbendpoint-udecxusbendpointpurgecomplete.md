---
UID: NF:udecxusbendpoint.UdecxUsbEndpointPurgeComplete
title: UdecxUsbEndpointPurgeComplete function (udecxusbendpoint.h)
description: Completes an asynchronous request for canceling all I/O requests queued to the specified endpoint.
old-location: buses\udecxusbendpointpurgecomplete.htm
tech.root: usbref
ms.assetid: 91257BC3-C469-44D5-96E2-D1FA599963F1
ms.date: 05/07/2018
ms.keywords: UdecxUsbEndpointPurgeComplete, UdecxUsbEndpointPurgeComplete function [Buses], buses.udecxusbendpointpurgecomplete, udecxusbendpoint/UdecxUsbEndpointPurgeComplete
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxUsbEndpointPurgeComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbEndpointPurgeComplete function


## -description


Completes an asynchronous request for canceling all I/O requests queued to the specified endpoint. 


## -parameters




### -param UdecxUsbEndpoint [in]

A handle to a UDE endpoint object. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627983">UdecxUsbEndpointCreate</a>.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595916">EVT_UDECX_USB_ENDPOINT_PURGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

