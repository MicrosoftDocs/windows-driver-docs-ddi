---
UID: NS:ucxendpoint._UCX_ENDPOINT_EVENT_CALLBACKS
title: _UCX_ENDPOINT_EVENT_CALLBACKS (ucxendpoint.h)
description: This structure provides a list of pointers to UCX endpoint event callback functions.
old-location: buses\_ucx_endpoint_event_callbacks.htm
tech.root: usbref
ms.assetid: 93071B7B-74D8-44A2-984D-A6BABFC07BA3
ms.date: 05/07/2018
keywords: ["_UCX_ENDPOINT_EVENT_CALLBACKS structure"]
ms.keywords: "*PUCX_ENDPOINT_EVENT_CALLBACKS, P_UCX_ENDPOINT_EVENT_CALLBACKS, P_UCX_ENDPOINT_EVENT_CALLBACKS structure pointer [Buses], UCX_ENDPOINT_EVENT_CALLBACKS, UCX_ENDPOINT_EVENT_CALLBACKS structure [Buses], _UCX_ENDPOINT_EVENT_CALLBACKS, buses._ucx_endpoint_event_callbacks, ucxendpoint/P_UCX_ENDPOINT_EVENT_CALLBACKS, ucxendpoint/_UCX_ENDPOINT_EVENT_CALLBACKS"
f1_keywords:
 - "ucxendpoint/UCX_ENDPOINT_EVENT_CALLBACKS"
 - "UCX_ENDPOINT_EVENT_CALLBACKS"
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
- UCX_ENDPOINT_EVENT_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_EVENT_CALLBACKS, *PUCX_ENDPOINT_EVENT_CALLBACKS
---

# _UCX_ENDPOINT_EVENT_CALLBACKS structure


## -description


This structure provides a list of  pointers to UCX endpoint event callback functions.


## -struct-fields




### -field Size

The size in bytes of the structure.


### -field EvtEndpointPurge

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_purge">EVT_UCX_ENDPOINT_PURGE</a> callback function.


### -field EvtEndpointStart

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_start">EVT_UCX_ENDPOINT_START</a> callback function.


### -field EvtEndpointAbort

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_abort">EVT_UCX_ENDPOINT_ABORT</a> callback function.


### -field EvtEndpointReset

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_reset">EVT_UCX_ENDPOINT_RESET</a> callback function.


### -field EvtEndpointOkToCancelTransfers

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_ok_to_cancel_transfers">EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS</a> callback function.


### -field EvtEndpointStaticStreamsAdd

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_static_streams_add">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a> callback function.


### -field EvtEndpointStaticStreamsEnable

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_static_streams_enable">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a> callback function.


### -field EvtEndpointStaticStreamsDisable

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_static_streams_disable">EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE</a> callback function.


### -field Reserved1

Do not use.


### -field EvtEndpointGetIsochTransferPathDelays

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_get_isoch_transfer_path_delays">EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS</a> callback function.


### -field EvtEndpointSetCharacteristic

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_set_characteristic">EVT_UCX_ENDPOINT_SET_CHARACTERISTIC</a> callback function.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucx_endpoint_event_callbacks_init">UCX_ENDPOINT_EVENT_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointinitseteventcallbacks">UcxEndpointInitSetEventCallbacks</a>
 

 

