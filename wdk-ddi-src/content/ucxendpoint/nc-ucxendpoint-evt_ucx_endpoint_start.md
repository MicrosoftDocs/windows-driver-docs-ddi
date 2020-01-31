---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_START
title: EVT_UCX_ENDPOINT_START (ucxendpoint.h)
description: The client driver's implementation that UCX calls to start the queue associated with the endpoint.
old-location: buses\evt_ucx_endpoint_start.htm
tech.root: usbref
ms.assetid: 8b801255-ee6a-413f-8ce3-3a3696283e6b
ms.date: 05/07/2018
ms.keywords: EVT_UCX_ENDPOINT_START, EVT_UCX_ENDPOINT_START callback, EvtUcxEndpointStart, EvtUcxEndpointStart callback function [Buses], PEVT_UCX_ENDPOINT_START, PEVT_UCX_ENDPOINT_START callback function pointer [Buses], buses.evt_ucx_endpoint_start, ucxendpoint/EvtUcxEndpointStart
f1_keywords:
 - "ucxendpoint/PEVT_UCX_ENDPOINT_START"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ucxendpoint.h
api_name:
- PEVT_UCX_ENDPOINT_START
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_ENDPOINT_START callback function


## -description


The client driver's implementation that UCX calls to start the queue associated with the endpoint.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param UcxEndpoint








#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.


## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
 method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
Endpoint_EvtUcxEndpointStart(
    UCXCONTROLLER   UcxController,
    UCXENDPOINT     UcxEndpoint
)

{
    UNREFERENCED_PARAMETER(UcxController);
    UNREFERENCED_PARAMETER(UcxEndpoint);

    DbgTrace(TL_INFO, Endpoint, "Endpoint_EvtUcxEndpointStart");
}</pre>
</td>
</tr>
</table></span></div>


