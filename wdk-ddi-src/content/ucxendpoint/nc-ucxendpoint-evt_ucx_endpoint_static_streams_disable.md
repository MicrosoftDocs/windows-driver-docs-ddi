---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
title: EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE (ucxendpoint.h)
description: The client driver's implementation that UCX calls to release controller resources for all streams for an endpoint.
old-location: buses\evt_ucx_endpoint_static_streams_disable.htm
tech.root: usbref
ms.assetid: 79da55ac-61de-40cc-b25b-421f7637a9fe
ms.date: 05/07/2018
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
 - PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
---

# EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE callback function


## -description

The client driver's implementation that UCX calls to release controller resources for all streams for an endpoint.

## -parameters

### -param UcxEndpoint

### -param UcxStaticStreams 

[in]
A handle to a UCX object that represents the static streams.

### -param Request 

[in]
Contains the URB for the <b>URB_FUNCTION_CLOSE_STATIC_STREAMS</b>.


#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
 method.

The client driver returns completion status in <i>Request</i> and in the USBD_STATUS
    in the URB header.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
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
}</pre>
</td>
</tr>
</table></span></div>

