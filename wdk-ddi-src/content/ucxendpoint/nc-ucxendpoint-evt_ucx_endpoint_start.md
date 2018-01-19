---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_START
title: EVT_UCX_ENDPOINT_START
author: windows-driver-content
description: The client driver's implementation that UCX calls to start the queue associated with the endpoint.
old-location: buses\evt_ucx_endpoint_start.htm
old-project: usbref
ms.assetid: 8b801255-ee6a-413f-8ce3-3a3696283e6b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
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
req.alt-api: PEVT_UCX_ENDPOINT_START
req.alt-loc: ucxendpoint.h
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


### -param Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.


## -returns
This callback function does not return a value.


## -remarks
The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
 method.</p>