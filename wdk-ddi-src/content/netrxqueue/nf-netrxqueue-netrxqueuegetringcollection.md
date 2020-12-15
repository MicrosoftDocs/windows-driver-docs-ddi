---
UID: NF:netrxqueue.NetRxQueueGetRingCollection
title: NetRxQueueGetRingCollection function (netrxqueue.h)
description: The NetRxQueueGetRingCollection function retrieves the NET_RING_COLLECTION structure for a receive (Rx) queue.
tech.root: netvista
ms.date: 01/31/2019
keywords: ["NetRxQueueGetRingCollection function"]
ms.keywords: NetRxQueueGetRingCollection
req.header: netrxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
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
targetos: Windows
f1_keywords:
 - NetRxQueueGetRingCollection
 - netrxqueue/NetRxQueueGetRingCollection
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NetRxQueueGetRingCollection
---

# NetRxQueueGetRingCollection function


## -description

The **NetRxQueueGetRingCollection** function retrieves the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure for a receive (Rx) queue.

## -parameters

### -param PacketQueue

A **NETPACKETQUEUE** structure. The client driver receives a pointer to this **NETPACKETQUEUE** structure in its *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* callback function.

## -returns

Returns a pointer to the queue's [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure.

## -remarks

Use the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure returned by this function to access a receive queue's net rings.

## -see-also

