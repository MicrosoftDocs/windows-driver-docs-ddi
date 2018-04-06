---
UID: NF:ufxclient.UfxEndpointInitSetEventCallbacks
title: UfxEndpointInitSetEventCallbacks function
author: windows-driver-content
description: Initialize a UFXENDPOINT_INIT structure.
old-location: buses\ufxendpointinitseteventcallbacks.htm
old-project: usbref
ms.assetid: D3D8D948-400A-47A0-98E9-ECF5643DB5D2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UfxEndpointInitSetEventCallbacks, UfxEndpointInitSetEventCallbacks method [Buses], buses.ufxendpointinitseteventcallbacks, ufxclient/UfxEndpointInitSetEventCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: ufxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxEndpointInitSetEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxEndpointInitSetEventCallbacks function


## -description


Initialize a <b>UFXENDPOINT_INIT</b> structure.


## -parameters




### -param EndpointInit [in, out]

Opaque structure passed by UFX in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187851">EVT_UFX_DEVICE_ENDPOINT_ADD</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/mt187849">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a>.


### -param Callbacks [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure.


## -returns



This method does not return a value.




## -remarks



The client driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a> from its <a href="https://msdn.microsoft.com/library/windows/hardware/mt187851">EVT_UFX_DEVICE_ENDPOINT_ADD</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/mt187849">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a> event callback function in order to create a new endpoint.

  The client driver first calls <a href="https://msdn.microsoft.com/library/windows/hardware/mt187976">UFX_ENDPOINT_CALLBACKS_INIT</a> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure. Then it calls <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a> with the initialized <b>UFX_ENDPOINT_CALLBACKS</b> structure.

For an code example that shows how to create a UFXENDPOINT object and initialize its context, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>.



