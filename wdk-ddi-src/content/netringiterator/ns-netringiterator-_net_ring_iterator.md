---
UID: NS:netringiterator._NET_RING_ITERATOR
title: NET_RING_ITERATOR
author: windows-driver-content
description: A NET_RING_ITERATOR is a small structure that contains references to the post and drain indices of a NET_RING to which it belongs.
tech.root: netvista
ms.assetid: 7f23a086-85dc-4880-9868-0c5314c840f2
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: struct
f1_keywords:
 - "netringiterator/NET_RING_ITERATOR"
ms.keywords: NET_RING_ITERATOR, NET_RING_ITERATOR, 
req.header: netringiterator.h
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
req.typenames: NET_RING_ITERATOR
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - netringiterator.h
api_name: 
 - NET_RING_ITERATOR
product:
- Windows
targetos: Windows
---

# NET_RING_ITERATOR structure

## -description



A **NET_RING_ITERATOR** is a small structure that contains references to the post and drain indices of a [**NET_RING**](../ring/ns-ring-_net_ring.md) to which it belongs.

## -struct-fields

### -field Rings

A [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure that describes the [**NET_RING**](../ring/ns-ring-_net_ring.md) structure to which this net ring iterator belongs.
 
### -field IndexToSet

The beginning of the range of elements that are covered by this iterator. This index does not move until after the client driver has finished processing elements in the ring and sets the iterator, which advances **IndexToSet** to **Index**.

Client drivers call [**NetPacketIteratorSet**](../netringiterator/nf-netringiterator-netpacketiteratorset.md) to set a packet iterator, or [**NetFragmentIteratorSet**](../netringiterator/nf-netringiterator-netfragmentiteratorset.md) to set a fragment iterator.
 
### -field Index

The iterator's current index in the [**NET_RING**](../ring/ns-ring-_net_ring.md). This index is advanced as the client driver processes elements in the ring.

Client drivers typically call [**NetPacketIteratorAdvance**](../netringiterator/nf-netringiterator-netpacketiteratoradvance.md) to advance a packet iterator, or [**NetFragmentIteratorAdvance**](../netringiterator/nf-netringiterator-netfragmentiteratoradvance.md) to advance a fragment iterator.
 
### -field End
 
The end of the range of elements in the net ring that is covered by this iterator.

## -remarks

NetAdapterCx client drivers should not use the **NET_RING_ITERATOR** structure directly. Instead, they should either use a [**NET_RING_PACKET_ITERATOR*](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) for a packet ring or a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) for a fragment ring.

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_PACKET_ITERATOR*](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)
