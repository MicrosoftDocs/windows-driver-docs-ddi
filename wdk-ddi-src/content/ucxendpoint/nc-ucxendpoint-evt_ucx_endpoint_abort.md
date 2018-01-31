---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_ABORT
title: EVT_UCX_ENDPOINT_ABORT
author: windows-driver-content
description: The client driver's implementation that UCX calls to abort the queue associated with the endpoint.
old-location: buses\evt_ucx_endpoint_abort.htm
old-project: usbref
ms.assetid: b457d0b5-30a2-42f9-9194-8c60af790f75
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ucx_endpoint_abort, EvtUcxEndpointAbort callback function [Buses], EvtUcxEndpointAbort, EVT_UCX_ENDPOINT_ABORT, EVT_UCX_ENDPOINT_ABORT, ucxendpoint/EvtUcxEndpointAbort, PEVT_UCX_ENDPOINT_ABORT callback function pointer [Buses], PEVT_UCX_ENDPOINT_ABORT
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
-	PEVT_UCX_ENDPOINT_ABORT
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product: Windows 10 or later.
---

# EVT_UCX_ENDPOINT_ABORT callback


## -description


The client driver's implementation that UCX calls to abort the queue associated with the endpoint.


## -prototype


````
EVT_UCX_ENDPOINT_ABORT EvtUcxEndpointAbort;

VOID EvtUcxEndpointAbort(
  _In_ UCXCONTROLLER UcxController,
  _In_ UCXENDPOINT   Endpoint
)
{ ... }

typedef EVT_UCX_ENDPOINT_ABORT PEVT_UCX_ENDPOINT_ABORT;
````


## -parameters




#### - UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param UcxEndpoint






#### - Endpoint [in]

A handle to a UCXENDPOINT object.


## -returns


This callback function does not return a value.



## -remarks


The client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
 method.

This function completes all requests associated with the endpoint, typically by calling <a href="..\wdfio\nf-wdfio-wdfioqueuestopandpurge.md">WdfIoQueueStopAndPurge</a>.


