---
UID: NF:ufxclient.UfxEndpointInitSetEventCallbacks
title: UfxEndpointInitSetEventCallbacks function
author: windows-driver-content
description: Initialize a UFXENDPOINT_INIT structure.
old-location: buses\ufxendpointinitseteventcallbacks.htm
old-project: usbref
ms.assetid: D3D8D948-400A-47A0-98E9-ECF5643DB5D2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UfxEndpointInitSetEventCallbacks
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
req.alt-api: UfxEndpointInitSetEventCallbacks
req.alt-loc: ufxclient.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxEndpointInitSetEventCallbacks function



## -description
Initialize a <b>UFXENDPOINT_INIT</b> structure.



## -syntax

````
VOID UfxEndpointInitSetEventCallbacks(
  [in, out] PUFXENDPOINT_INIT       EndpointInit,
  [in]      PUFX_ENDPOINT_CALLBACKS Callbacks
);
````


## -parameters

### -param EndpointInit [in, out]

Opaque structure passed by UFX in the call to <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_endpoint_add.md">EVT_UFX_DEVICE_ENDPOINT_ADD</a> or <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_default_endpoint_add.md">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a>.


### -param Callbacks [in]

Pointer to a <a href="..\ufxclient\ns-ufxclient-_ufx_endpoint_callbacks.md">UFX_ENDPOINT_CALLBACKS</a> structure.


## -returns
This method does not return a value.


## -remarks
The client driver calls <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a> from its <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_endpoint_add.md">EVT_UFX_DEVICE_ENDPOINT_ADD</a> or <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_default_endpoint_add.md">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a> event callback function in order to create a new endpoint.

  The client driver first calls <a href="..\ufxclient\nf-ufxclient-ufx_endpoint_callbacks_init.md">UFX_ENDPOINT_CALLBACKS_INIT</a> to initialize a <a href="..\ufxclient\ns-ufxclient-_ufx_endpoint_callbacks.md">UFX_ENDPOINT_CALLBACKS</a> structure. Then it calls <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a> with the initialized <b>UFX_ENDPOINT_CALLBACKS</b> structure.

For an code example that shows how to create a UFXENDPOINT object and initialize its context, see the Remarks section of <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.</p>