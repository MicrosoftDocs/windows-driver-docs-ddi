---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
title: EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
author: windows-driver-content
description: The client driver's implementation that UCX calls to release controller resources for all streams for an endpoint.
old-location: buses\evt_ucx_endpoint_static_streams_disable.htm
old-project: usbref
ms.assetid: 79da55ac-61de-40cc-b25b-421f7637a9fe
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE, EvtUcxEndpointStaticStreamsDisable, EvtUcxEndpointStaticStreamsDisable callback function [Buses], PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE, PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE callback function pointer [Buses], buses.evt_ucx_endpoint_static_streams_disable, ucxendpoint/EvtUcxEndpointStaticStreamsDisable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ucxendpoint.h
api_name:
-	PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product: Windows 10 or later.
---

# EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE callback


## -description


The client driver's implementation that UCX calls to release controller resources for all streams for an endpoint.


## -prototype


````
EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE EvtUcxEndpointStaticStreamsDisable;

VOID EvtUcxEndpointStaticStreamsDisable(
  _In_ UCXENDPOINT Endpoint,
  _In_ UCXSSTREAMS UcxStaticStreams,
  _In_ WDFREQUEST  Request
)
{ ... }

typedef EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE;
````


## -parameters




### -param UcxEndpoint


### -param UcxStaticStreams [in]

A handle to a UCX object that represents the static streams.


### -param Request [in]

Contains the URB for the <b>URB_FUNCTION_CLOSE_STATIC_STREAMS</b>.


#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
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


