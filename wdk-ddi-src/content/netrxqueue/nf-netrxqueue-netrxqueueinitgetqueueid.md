---
UID: NF:netrxqueue.NetRxQueueInitGetQueueId
title: NetRxQueueInitGetQueueId function (netrxqueue.h)
description: Retrieves the identifier of the receive queue associated with a receive queue.
tech.root: netvista
ms.assetid: 588df434-c3f8-4a4a-a9ae-330a825c1d48
ms.date: 02/09/2018
keywords: ["NetRxQueueInitGetQueueId function"]
ms.keywords: NetRxQueueInitGetQueueId
req.header: netrxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.21
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.alt-api: 
req.alt-loc: 
targetos: Windows
f1_keywords:
 - NetRxQueueInitGetQueueId
 - netrxqueue/NetRxQueueInitGetQueueId
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netrxqueue.h
api_name:
 - NetRxQueueInitGetQueueId
---

# NetRxQueueInitGetQueueId function


## -description

Retrieves the identifier of the receive queue associated with a receive queue.

## -parameters

### -param NetRxQueueInit

A pointer to a NetAdapterCx-allocated **NETRXQUEUE_INIT** structure. For more information, see the Remarks section.

## -returns

Returns a ULONG that identifies a receive queue.

## -remarks

The client driver receives a pointer to a **NETRXQUEUE_INIT** structure in its *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* callback function.

Starting with zero, NetAdapterCx assigns an unique identifier value for each queue that it creates. The client driver specifies the number of transmit queues that the network adapter supports in the **MaximumNumberOfQueues** member of the [NET_ADAPTER_RX_CAPABILITIES](../netadapter/ns-netadapter-_net_adapter_rx_capabilities.md) structure, which is initialized and passed to [NetAdapterSetDataPathCapabilities](../netadapter/nf-netadapter-netadaptersetdatapathcapabilities.md) when starting the net adapter. Identifier values range from zero to the value of `(((MaxNumber of TxQueues) + (MaxNumber of RxQueues)) - 1)`.

## -see-also

