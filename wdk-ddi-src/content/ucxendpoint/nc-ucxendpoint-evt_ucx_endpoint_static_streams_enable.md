---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE
title: EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE (ucxendpoint.h)
description: The client driver's implementation that UCX calls to enable the static streams.
old-location: buses\evt_ucx_endpoint_static_streams_enable.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE callback function"]
ms.keywords: EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE, EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE callback, EvtUcxEndpointStaticStreamsEnable, EvtUcxEndpointStaticStreamsEnable callback function [Buses], PFN_UCM_CONNECTOR_GET_OPERATING_MODE, PFN_UCM_CONNECTOR_GET_OPERATING_MODE callback function pointer [Buses], buses.evt_ucx_endpoint_static_streams_enable, ucxendpoint/EvtUcxEndpointStaticStreamsEnable
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
 - EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE
 - ucxendpoint/EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxendpoint.h
api_name:
 - PFN_UCM_CONNECTOR_GET_OPERATING_MODE
---

# EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE callback function


## -description

The client driver's implementation that UCX calls to enable the static streams.

## -parameters

### -param UcxEndpoint

### -param UcxStaticStreams 

[in]
A handle to a UCX object that represents the static streams.

### -param Request 

[in]
Contains the URB for the <b>URB_FUNCTION_OPEN_STATIC_STREAMS</b>.


#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
 method.

The client driver returns completion status in <i>Request</i> and in the USBD_STATUS
    in the URB header.  The driver can complete the WDFREQUEST asynchronously.


#### Examples


```
VOID
Endpoint_EvtUcxEndpointStaticStreamsEnable(
    UCXENDPOINT     UcxEndpoint,
    UCXSSTREAMS     UcxStaticStreams,
    WDFREQUEST      Request
)

{
    UNREFERENCED_PARAMETER(UcxEndpoint);
    UNREFERENCED_PARAMETER(UcxStaticStreams);

    DbgTrace(TL_INFO, Endpoint, "Endpoint_EvtUcxEndpointStaticStreamsEnable");

    WdfRequestComplete(Request, STATUS_SUCCESS);
}
```
