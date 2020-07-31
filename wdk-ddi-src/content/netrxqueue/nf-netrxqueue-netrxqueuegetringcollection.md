---
UID: NF:netrxqueue.NetRxQueueGetRingCollection
title: NetRxQueueGetRingCollection function (netrxqueue.h)
description: The NetRxQueueGetRingCollection method retrieves the NET_RING_COLLECTION structure for a receive (Rx) queue.
tech.root: netvista
ms.assetid: 18ae9b71-b6a3-4a6f-ab70-74332b852338
ms.date: 01/31/2019
keywords: ["NetRxQueueGetRingCollection function"]
f1_keywords:
 - "netrxqueue/NetRxQueueCreate"
 - "NetRxQueueCreate"
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
topictype: 
- apiref
apitype: 
- DllExport
apilocation: 
- NtosKrnl.exe
apiname: 
- NetRxQueueGetRingCollection
targetos: Windows

---

# NetRxQueueGetRingCollection function


## -description


The **NetRxQueueGetRingCollection** method retrieves the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure for a receive (Rx) queue.

## -parameters

### -param PacketQueue

A **NETPACKETQUEUE** structure. The client driver receives a pointer to this **NETPACKETQUEUE** structure in its *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* callback function.

## -returns

Returns a pointer to the queue's [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure.

## -remarks

Use the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure returned by this method to access a receive queue's net rings.

## -see-also
