---
UID: NS:ucxendpoint._UCX_ENDPOINT_EVENT_CALLBACKS
title: "_UCX_ENDPOINT_EVENT_CALLBACKS"
author: windows-driver-content
description: This structure provides a list of pointers to UCX endpoint event callback functions.
old-location: buses\_ucx_endpoint_event_callbacks.htm
old-project: usbref
ms.assetid: 93071B7B-74D8-44A2-984D-A6BABFC07BA3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCX_ENDPOINT_EVENT_CALLBACKS, P_UCX_ENDPOINT_EVENT_CALLBACKS, P_UCX_ENDPOINT_EVENT_CALLBACKS structure pointer [Buses], UCX_ENDPOINT_EVENT_CALLBACKS, UCX_ENDPOINT_EVENT_CALLBACKS structure [Buses], _UCX_ENDPOINT_EVENT_CALLBACKS, buses._ucx_endpoint_event_callbacks, ucxendpoint/P_UCX_ENDPOINT_EVENT_CALLBACKS, ucxendpoint/_UCX_ENDPOINT_EVENT_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
-	UCX_ENDPOINT_EVENT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_EVENT_CALLBACKS, *PUCX_ENDPOINT_EVENT_CALLBACKS
req.product: Windows 10 or later.
---

# _UCX_ENDPOINT_EVENT_CALLBACKS structure


## -description


This structure provides a list of  pointers to UCX endpoint event callback functions.


## -struct-fields




### -field Size

The size in bytes of the structure.


### -field EvtEndpointPurge

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187827">EVT_UCX_ENDPOINT_PURGE</a> callback function.


### -field EvtEndpointStart

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187829">EVT_UCX_ENDPOINT_START</a> callback function.


### -field EvtEndpointAbort

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187825">EVT_UCX_ENDPOINT_ABORT</a> callback function.


### -field EvtEndpointReset

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187828">EVT_UCX_ENDPOINT_RESET</a> callback function.


### -field EvtEndpointOkToCancelTransfers

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187826">EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS</a> callback function.


### -field EvtEndpointStaticStreamsAdd

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187830">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a> callback function.


### -field EvtEndpointStaticStreamsEnable

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187832">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a> callback function.


### -field EvtEndpointStaticStreamsDisable

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187831">EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE</a> callback function.


### -field Reserved1

Do not use.


### -field EvtEndpointGetIsochTransferPathDelays

A pointer to an <a href="https://msdn.microsoft.com/E400CCAE-8F0F-4814-8B63-EB4E116543A2">EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS</a> callback function.


### -field EvtEndpointSetCharacteristic

A pointer to an <a href="https://msdn.microsoft.com/4FA3F175-52E4-472D-A9B3-B3B4B37E1701">EVT_UCX_ENDPOINT_SET_CHARACTERISTIC</a> callback function.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188064">UCX_ENDPOINT_EVENT_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188041">UcxEndpointInitSetEventCallbacks</a>
 

 

