---
UID: NF:ucxendpoint.UCX_ENDPOINT_EVENT_CALLBACKS_INIT
title: UCX_ENDPOINT_EVENT_CALLBACKS_INIT function
author: windows-driver-content
description: Initializes a UCX_ENDPOINT_EVENT_CALLBACKS structure with client driver's callback functions. The client driver calls this function before calling UcxEndpointCreate method to create an endpoint and register its callback functions with UCX.
old-location: buses\_ucx_endpoint_event_callbacks_init.htm
old-project: usbref
ms.assetid: 1890052A-EE98-4749-ACF9-8321148F3828
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: UCX_ENDPOINT_EVENT_CALLBACKS_INIT, UCX_ENDPOINT_EVENT_CALLBACKS_INIT function [Buses], buses._ucx_endpoint_event_callbacks_init, ucxendpoint/UCX_ENDPOINT_EVENT_CALLBACKS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxendpoint.h
req.include-header: Ucxclass.h
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
-	UCX_ENDPOINT_EVENT_CALLBACKS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCX_ENDPOINT_EVENT_CALLBACKS_INIT function


## -description


Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188063">UCX_ENDPOINT_EVENT_CALLBACKS</a> structure with client driver's callback functions. The client driver calls this function before calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a> method to create an endpoint and register its callback functions with UCX.


## -parameters




### -param Callbacks [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188063">UCX_ENDPOINT_EVENT_CALLBACKS</a> structure that contains pointers to the client driver's event callback functions.


### -param EvtEndpointPurge [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187827">EVT_UCX_ENDPOINT_PURGE</a>                     event callback function.


### -param EvtEndpointStart [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187829">EVT_UCX_ENDPOINT_START</a>                     event callback function.


### -param EvtEndpointAbort [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187825">EVT_UCX_ENDPOINT_ABORT</a>                     event callback function.


### -param EvtEndpointReset [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187828">EVT_UCX_ENDPOINT_RESET</a>                     event callback function.


### -param EvtEndpointOkToCancelTransfers [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187826">EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS</a>    event callback function.


### -param EvtEndpointStaticStreamsAdd [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187830">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a>        event callback function.


### -param EvtEndpointStaticStreamsEnable [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187832">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a>     event callback function.


### -param EvtEndpointStaticStreamsDisable [in]

A pointer to client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187831">EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE</a>    event callback function.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 

 

