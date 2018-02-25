---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_START
title: EVT_UCX_ENDPOINT_START
author: windows-driver-content
description: The client driver's implementation that UCX calls to start the queue associated with the endpoint.
old-location: buses\evt_ucx_endpoint_start.htm
old-project: UsbRef
ms.assetid: 8b801255-ee6a-413f-8ce3-3a3696283e6b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: EVT_UCX_ENDPOINT_START, EvtUcxEndpointStart, EvtUcxEndpointStart callback function [Buses], PEVT_UCX_ENDPOINT_START, PEVT_UCX_ENDPOINT_START callback function pointer [Buses], buses.evt_ucx_endpoint_start, ucxendpoint/EvtUcxEndpointStart
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ucxendpoint.h
apiname:
-	PEVT_UCX_ENDPOINT_START
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product: Windows 10 or later.
---

# EVT_UCX_ENDPOINT_START callback


## -description


The client driver's implementation that UCX calls to start the queue associated with the endpoint.


## -prototype


````
EVT_UCX_ENDPOINT_START EvtUcxEndpointStart;

VOID EvtUcxEndpointStart(
  _In_ UCXCONTROLLER UcxController,
  _In_ UCXENDPOINT   Endpoint
)
{ ... }

typedef EVT_UCX_ENDPOINT_START PEVT_UCX_ENDPOINT_START;
````


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param UcxEndpoint








#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
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


