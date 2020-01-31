---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_PURGE
title: EVT_UCX_ENDPOINT_PURGE (ucxendpoint.h)
description: The client driver's implementation that completes all outstanding I/O requests on the endpoint.
old-location: buses\evt_ucx_endpoint_purge.htm
tech.root: usbref
ms.assetid: e4ceb597-ebfe-4016-ba83-e5246a70f566
ms.date: 05/07/2018
ms.keywords: EVT_UCX_ENDPOINT_PURGE, EVT_UCX_ENDPOINT_PURGE callback, EvtUcxEndpointPurge, EvtUcxEndpointPurge callback function [Buses], PEVT_UCX_ENDPOINT_PURGE, PEVT_UCX_ENDPOINT_PURGE callback function pointer [Buses], buses.evt_ucx_endpoint_purge, ucxendpoint/EvtUcxEndpointPurge
f1_keywords:
 - "ucxendpoint/PEVT_UCX_ENDPOINT_PURGE"
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
- PEVT_UCX_ENDPOINT_PURGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_ENDPOINT_PURGE callback function


## -description


The client driver's implementation that completes all outstanding I/O requests on the endpoint.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param UcxEndpoint








#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.


## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
 method.

Typically, this function calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>.

After UCX calls this function, the client driver fails subsequent I/O requests until UCX calls the client driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_start">EVT_UCX_ENDPOINT_START</a> callback function.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
Endpoint_UcxEvtEndpointPurge(
    UCXCONTROLLER   UcxController,
    UCXENDPOINT     UcxEndpoint
    )
{
            WdfIoQueuePurge(endpointContext->WdfQueue,
                            Endpoint_WdfEvtPurgeComplete,
                            UcxEndpoint);
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>
 

 

