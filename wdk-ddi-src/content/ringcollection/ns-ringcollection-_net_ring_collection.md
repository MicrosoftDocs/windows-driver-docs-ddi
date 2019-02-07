---
UID: NS:ringcollection._NET_RING_COLLECTION
title: _NET_RING_COLLECTION (ringcollection.h)
description: The NET_RING_COLLECTION structure describes the collection of net rings that belong to a packet queue.
tech.root: netvista
ms.assetid: 0E384B79-9277-43DD-A28E-0C0D39559847
ms.date: 02/06/2019
ms.topic: struct
ms.keywords: _NET_RING_COLLECTION, NET_RING_COLLECTION, *PNET_RING_COLLECTION, 
req.header: ringcollection.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_RING_COLLECTION
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	ringcollection.h
apiname: 
-	NET_RING_COLLECTION
product:
-	Windows
targetos: Windows
product:
- Windows
---

# _NET_RING_COLLECTION structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_RING_COLLECTION** structure describes the collection of net rings that belong to a packet queue.

## -struct-fields

### -field Rings

A pointer to an array of [**NET_RING**](../ring/ns-ring-_net_ring.md) structures.

## -remarks

Call [**NetRxQueueGetRingCollection**](../netrxqueue/nf-netrxqueue-netrxqueuegetringcollection.md) or [**NetTxQueueGetRingCollection**](../nettxqueue/nf-nettxqueue-nettxqueuegetringcollection.md) to get a packet queue's ring collection. You can then use this collection structure to retrieve iterators for processing the queue's packet ring and fragment ring. For more information about using net rings and net ring iterators, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)