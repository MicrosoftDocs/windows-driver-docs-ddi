---
UID: NF:netringiterator.NetRingGetAllPackets
title: NetRingGetAllPackets function
author: windows-driver-content
description: The NetRingGetAllPackets method gets a packet iterator for the entire range that a client driver owns in a packet ring.
tech.root: netvista
ms.assetid: a218f2b3-25a7-45e0-88f7-48ed7f92a289
ms.author: windowsdriverdev
ms.date: 02/01/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetRingGetAllPackets"
ms.keywords: NetRingGetAllPackets
req.header: netringiterator.h
req.include-header:
req.target-type:
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- netringiterator.h
api_name: 
- NetRingGetAllPackets
product: Windows
targetos: Windows

---

# NetRingGetAllPackets function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetRingGetAllPackets** method gets a packet iterator for the entire range that a client driver owns in a packet ring.

## -parameters

### -param Rings

A pointer to the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) struture that describes this packet queue's net rings.

## -returns

Returns a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) that begins at the packet ring's **BeginIndex** and ends at the packet ring's **EndIndex**. In other words, the iterator covers all packets in the ring that the driver currently owns, including the post subsection and the drain subsection.

## -remarks

Client drivers typically call **NetRingGetAllPackets** to begin performing operations on all packets that they own in a packet ring. This might include processing a batch of receives that span all available packets in the ring, or draining the ring during data path cancellation.

For an animation and code example of using this method, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)
