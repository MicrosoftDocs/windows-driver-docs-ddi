---
UID: NF:udecxusbendpoint.UdecxUsbEndpointInitSetCallbacks
title: UdecxUsbEndpointInitSetCallbacks function
author: windows-driver-content
description: Sets pointers to UDE client driver-implemented callback functions in the initialization parameters of the simple endpoint to create.
old-location: buses\udecxusbendpointinitsetcallbacks.htm
old-project: usbref
ms.assetid: 0F6EBBDA-FA0B-4044-905B-535D4FFEC5D2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UdecxUsbEndpointInitSetCallbacks, UdecxUsbEndpointInitSetCallbacks function [Buses], buses.udecxusbendpointinitsetcallbacks, udecxusbendpoint/UdecxUsbEndpointInitSetCallbacks
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
-	UdecxUsbEndpointInitSetCallbacks
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---

# UdecxUsbEndpointInitSetCallbacks function


## -description


Sets pointers to UDE client driver-implemented  callback functions in the initialization parameters of the simple endpoint to create.


## -syntax


````
FORCEINLINE void UdecxUsbEndpointInitSetCallbacks(
  _Inout_ PUDECXUSBENDPOINT_INIT        Init,
  _In_    PUDECX_USB_ENDPOINT_CALLBACKS EndpointCallbacks
);
````


## -parameters




### -param UdecxUsbEndpointInit

TBD


### -param EndpointCallbacks [in]

A pointer to <a href="..\udecxusbendpoint\ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks.md">UDECX_USB_ENDPOINT_CALLBACKS</a> that contains function pointers to event callback functions implemented by the UDE client driver. 


#### - Init [in, out]

A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate.md">UdecxUsbSimpleEndpointInitAllocate</a>.


## -returns



This function does not return a value.




## -see-also

<a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 


