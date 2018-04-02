---
UID: NF:udecxusbendpoint.UdecxUsbEndpointInitFree
title: UdecxUsbEndpointInitFree function
author: windows-driver-content
description: Release the resources that were allocated by the UdecxUsbSimpleEndpointInitAllocate call.
old-location: buses\udecxusbendpointinitfree.htm
old-project: usbref
ms.assetid: F95BDA95-4667-4EC3-9FE5-C78B453AC0B3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UdecxUsbEndpointInitFree, UdecxUsbEndpointInitFree function [Buses], buses.udecxusbendpointinitfree, udecxusbendpoint/UdecxUsbEndpointInitFree
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	UdecxUsbEndpointInitFree
product:
- Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---

# UdecxUsbEndpointInitFree function


## -description


Release the resources that were allocated by the  <a href="https://msdn.microsoft.com/library/windows/hardware/mt627989">UdecxUsbSimpleEndpointInitAllocate</a> call.


## -parameters




### -param Init [in]

A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627989">UdecxUsbSimpleEndpointInitAllocate</a>.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627983">UdecxUsbEndpointCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

