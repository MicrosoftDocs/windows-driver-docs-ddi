---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
title: EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE (ucxendpoint.h)
description: The client driver's implementation that UCX calls to release controller resources for all streams for an endpoint.
old-location: buses\evt_ucx_endpoint_static_streams_disable.htm
tech.root: usbref
ms.date: 01/14/2022
keywords: ["EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE callback function"]
ms.keywords: EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE, EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE callback, EvtUcxEndpointStaticStreamsDisable, EvtUcxEndpointStaticStreamsDisable callback function [Buses], PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE, PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE callback function pointer [Buses], buses.evt_ucx_endpoint_static_streams_disable, ucxendpoint/EvtUcxEndpointStaticStreamsDisable
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
 - ucxendpoint/EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxendpoint.h
api_name:
 - EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
---

# EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE callback function

## -description

The client driver's implementation that UCX calls to release controller resources for all streams for an endpoint.

## -parameters

### -param UcxEndpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.

### -param UcxStaticStreams [in]

A handle to a UCX object that represents the static streams.

### -param Request [in]

Contains the URB for the **URB_FUNCTION_CLOSE_STATIC_STREAMS**.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the [UcxEndpointCreate](nf-ucxendpoint-ucxendpointcreate.md) method.

The client driver returns completion status in *Request* and in the USBD_STATUS in the URB header. The driver can complete the WDFREQUEST asynchronously.

### Examples

```cpp
VOID
Endpoint_EvtUcxEndpointStaticStreamsDisable(
    UCXENDPOINT     UcxEndpoint,
    UCXSSTREAMS     UcxStaticStreams,
    WDFREQUEST      Request
)

{
    UNREFERENCED_PARAMETER(UcxEndpoint);
    UNREFERENCED_PARAMETER(UcxStaticStreams);

    DbgTrace(TL_INFO, Endpoint, "Endpoint_EvtUcxEndpointStaticStreamsDisable");

    WdfRequestComplete(Request, STATUS_SUCCESS);
}
```
