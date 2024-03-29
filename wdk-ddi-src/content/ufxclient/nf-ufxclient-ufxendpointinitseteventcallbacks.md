---
UID: NF:ufxclient.UfxEndpointInitSetEventCallbacks
title: UfxEndpointInitSetEventCallbacks function (ufxclient.h)
description: Initialize a UFXENDPOINT_INIT structure.
old-location: buses\ufxendpointinitseteventcallbacks.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UfxEndpointInitSetEventCallbacks function"]
ms.keywords: UfxEndpointInitSetEventCallbacks, UfxEndpointInitSetEventCallbacks method [Buses], buses.ufxendpointinitseteventcallbacks, ufxclient/UfxEndpointInitSetEventCallbacks
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UfxEndpointInitSetEventCallbacks
 - ufxclient/UfxEndpointInitSetEventCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ufxclient.h
api_name:
 - UfxEndpointInitSetEventCallbacks
---

# UfxEndpointInitSetEventCallbacks function


## -description

Initialize a <b>UFXENDPOINT_INIT</b> structure.

## -parameters

### -param EndpointInit [in, out]


Opaque structure passed by UFX in the call to <a href="/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_endpoint_add">EVT_UFX_DEVICE_ENDPOINT_ADD</a> or <a href="/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_default_endpoint_add">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a>.

### -param Callbacks [in]


Pointer to a <a href="/windows-hardware/drivers/ddi/ufxclient/ns-ufxclient-_ufx_endpoint_callbacks">UFX_ENDPOINT_CALLBACKS</a> structure.

## -remarks

The client driver calls <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a> from its <a href="/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_endpoint_add">EVT_UFX_DEVICE_ENDPOINT_ADD</a> or <a href="/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_default_endpoint_add">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a> event callback function in order to create a new endpoint.

  The client driver first calls <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufx_endpoint_callbacks_init">UFX_ENDPOINT_CALLBACKS_INIT</a> to initialize a <a href="/windows-hardware/drivers/ddi/ufxclient/ns-ufxclient-_ufx_endpoint_callbacks">UFX_ENDPOINT_CALLBACKS</a> structure. Then it calls <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a> with the initialized <b>UFX_ENDPOINT_CALLBACKS</b> structure.

For an code example that shows how to create a UFXENDPOINT object and initialize its context, see the Remarks section of <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.
