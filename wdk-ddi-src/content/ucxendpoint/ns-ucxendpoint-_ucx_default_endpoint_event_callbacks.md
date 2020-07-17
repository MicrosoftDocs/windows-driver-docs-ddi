---
UID: NS:ucxendpoint._UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS
title: _UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS (ucxendpoint.h)
description: This structure provides a list of UCX default endpoint event callback functions.
old-location: buses\_ucx_default_endpoint_event_callbacks.htm
tech.root: usbref
ms.assetid: A22E96FC-E219-4F6C-B8AF-AC86FAD89543
ms.date: 05/07/2018
keywords: ["_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure"]
ms.keywords: "*PUCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure pointer [Buses], UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure [Buses], _UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, buses._ucx_default_endpoint_event_callbacks, ucxendpoint/P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, ucxendpoint/_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS"
f1_keywords:
 - "ucxendpoint/UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS"
 - "UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucxendpoint.h
api_name:
- UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, *PUCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS
---

# _UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure


## -description


This structure provides a list of UCX default endpoint event callback functions.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field EvtEndpointPurge

A pointer to a EVT_UCX_ENDPOINT_PURGE callback function.


### -field EvtEndpointStart

A pointer to a EVT_UCX_ENDPOINT_START callback function.


### -field EvtEndpointAbort

A pointer to a EVT_UCX_ENDPOINT_ABORT callback function.


### -field EvtEndpointOkToCancelTransfers

A pointer to a EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function.


### -field EvtDefaultEndpointUpdate

A pointer to a EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function.


### -field Reserved1

Do not use.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucx_default_endpoint_event_callbacks_init">UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxdefaultendpointinitseteventcallbacks">UcxDefaultEndpointInitSetEventCallbacks</a>
 

 

