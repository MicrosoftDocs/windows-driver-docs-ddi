---
UID: NC:ucxendpoint.EVT_UCX_DEFAULT_ENDPOINT_UPDATE
title: EVT_UCX_DEFAULT_ENDPOINT_UPDATE
author: windows-driver-content
description: The client driver's implementation that UCX calls with information about the default endpoint.
old-location: buses\evt_ucx_default_endpoint_update.htm
tech.root: usbref
ms.assetid: 0a67ef0a-07ec-43d3-9a25-b28192677b35
ms.date: 05/07/2018
ms.keywords: EVT_UCX_DEFAULT_ENDPOINT_UPDATE, EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback, EvtUcxDefaultEndpointUpdate, EvtUcxDefaultEndpointUpdate callback function [Buses], PEVT_UCX_DEFAULT_ENDPOINT_UPDATE, PEVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function pointer [Buses], buses.evt_ucx_default_endpoint_update, ucxendpoint/EvtUcxDefaultEndpointUpdate
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
-	PEVT_UCX_DEFAULT_ENDPOINT_UPDATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function


## -description


The client driver's implementation that UCX calls with information about the default endpoint.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param Request [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188018">DEFAULT_ENDPOINT_UPDATE</a> structure that contains the handle to the default endpoint to be updated.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers its <i>EVT_UCX_DEFAULT_ENDPOINT_UPDATE</i> implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 method.

UCX typically calls this routine to update the default endpoint's maximum packet size.  The client driver returns completion status in the WDFREQUEST, which it can complete
    asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
Endpoint_EvtUcxDefaultEndpointUpdate(
    UCXCONTROLLER   UcxController,
    WDFREQUEST      Request
)

{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, Endpoint, "Endpoint_EvtUcxDefaultEndpointUpdate");

    WDF_REQUEST_PARAMETERS_INIT(&amp;wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &amp;wdfRequestParams);

    defaultEndpointUpdate = (PDEFAULT_ENDPOINT_UPDATE)wdfRequestParams.Parameters.Others.Arg1;
    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187950">UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188037">UcxDefaultEndpointInitSetEventCallbacks</a>
 

 

