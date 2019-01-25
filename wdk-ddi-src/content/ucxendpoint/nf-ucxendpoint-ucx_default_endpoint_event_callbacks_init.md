---
UID: NF:ucxendpoint.UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT
title: UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT function (ucxendpoint.h)
description: Initializes a UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure with client driver's callback functions. The client driver calls this function before calling UcxEndpointCreate method to create an endpoint and register its callback functions with UCX.
old-location: buses\ucx_default_endpoint_event_callbacks_init.htm
tech.root: usbref
ms.assetid: EE7ABC3D-948B-481B-B254-40A05EDEB83D
ms.date: 05/07/2018
ms.keywords: UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT, UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT function [Buses], buses.ucx_default_endpoint_event_callbacks_init, ucxendpoint/UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT
ms.topic: function
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxendpoint.h
api_name:
-	UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT function


## -description


Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188062">UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS</a> structure with client driver's callback functions. The client driver calls this function before calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a> method to create an endpoint and register its callback functions with UCX.


## -parameters




### -param Callbacks [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188062">UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS</a> structure that contains pointers to the client driver's event callback functions.


### -param EvtEndpointPurge [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187827">EVT_UCX_ENDPOINT_PURGE</a>                     event callback function.


### -param EvtEndpointStart [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187829">EVT_UCX_ENDPOINT_START</a>                     event callback function.


### -param EvtEndpointAbort [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187825">EVT_UCX_ENDPOINT_ABORT</a>                     event callback function.


### -param EvtEndpointOkToCancelTransfers [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187826">EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS</a>    event callback function.


### -param EvtDefaultEndpointUpdate [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187824">EVT_UCX_DEFAULT_ENDPOINT_UPDATE</a>    event callback function.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 

 

