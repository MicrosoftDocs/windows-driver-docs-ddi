---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_RESET
title: EVT_UCX_ENDPOINT_RESET (ucxendpoint.h)
description: The client driver's implementation that UCX calls to reset the controller’s programming for an endpoint.
old-location: buses\evt_ucx_endpoint_reset.htm
tech.root: usbref
ms.assetid: 927fdd48-416e-4e8f-a29c-c2799952197e
ms.date: 05/07/2018
ms.keywords: EVT_UCX_ENDPOINT_RESET, EVT_UCX_ENDPOINT_RESET callback, EvtUcxEndpointReset, EvtUcxEndpointReset callback function [Buses], PEVT_UCX_ENDPOINT_RESET, PEVT_UCX_ENDPOINT_RESET callback function pointer [Buses], buses.evt_ucx_endpoint_reset, ucxendpoint/EvtUcxEndpointReset
f1_keywords:
 - "ucxendpoint/PEVT_UCX_ENDPOINT_RESET"
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
- PEVT_UCX_ENDPOINT_RESET
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_ENDPOINT_RESET callback function


## -description


The client driver's implementation that UCX calls to reset the controller’s programming for an endpoint.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param UcxEndpoint


### -param Request [in]

A handle to a framework request object that the client driver completes when the reset operation is finished.


#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.


## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
 method.

The client driver returns completion status in the WDFREQUEST, which it might complete
    asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
Endpoint_EvtUcxEndpointReset(
    UCXCONTROLLER   UcxController,
    UCXENDPOINT     UcxEndpoint,
    WDFREQUEST      Request
)

{
    UNREFERENCED_PARAMETER(UcxController);
    UNREFERENCED_PARAMETER(UcxEndpoint);

    DbgTrace(TL_INFO, Endpoint, "Endpoint_EvtUcxEndpointReset");

    WdfRequestComplete(Request, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>


