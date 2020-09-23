---
UID: NF:ringcollection.NetRingCollectionGetPacketRing
title: NetRingCollectionGetPacketRing function (ringcollection.h)
description: The NetRingCollectionGetPacketRing gets the packet ring for a packet queue.
tech.root: netvista
ms.assetid: D4B33AEA-64FD-42F4-BADB-3CF9A1D0BBC6
ms.date: 02/06/2019
keywords: ["NetRingCollectionGetPacketRing function"]
ms.keywords: NetRingCollectionGetPacketRing
req.header: ringcollection.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: Any level as long as target memory is resident
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
 - NetRingCollectionGetPacketRing
 - ringcollection/NetRingCollectionGetPacketRing
topictype:
 - apiref
apitype:
 - HeaderDef
apilocation:
 - ringcollection.h
apiname:
 - NetRingCollectionGetPacketRing
---

# NetRingCollectionGetPacketRing function


## -description

The **NetRingCollectionGetPacketRing** gets the packet ring for a packet queue.

## -parameters

### -param Rings

A pointer to a [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure that describes this packet queue's net rings.

## -returns

Returns a pointer to the packet [**NET_RING**](../ring/ns-ring-_net_ring.md) for the packet queue.

## -remarks

Client drivers typically call this function when they need information about a packet ring, such as the number of elements in the ring. For example, during its queue initialization routines a client driver might need to allocate memory for hardware descriptors in a one-to-one ratio to the number of packets in the packet ring.

## -see-also

[Introduction to net rings](/windows-hardware/drivers/netcx/introduction-to-net-rings)