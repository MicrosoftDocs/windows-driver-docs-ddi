---
UID: NF:netringiterator.NetRingGetPostPackets
title: NetRingGetPostPackets function
author: windows-driver-content
description: The NetRingGetPostPackets method gets a packet iterator for the post subsection of a packet ring.
tech.root: netvista
ms.assetid: 61882945-93a3-4e2c-8654-e4de24181b5d
ms.author: windowsdriverdev
ms.date: 02/01/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetRingGetPostPackets"
ms.keywords: NetRingGetPostPackets
req.header: netringiterator.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib: netadaptercxstub.lib
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
- NetRingGetPostPackets
product:
- Windows
targetos: Windows

---

# NetRingGetPostPackets function


## -description



The **NetRingGetPostPackets** method gets a packet iterator for the post subsection of a packet ring.

## -parameters

### -param Rings

A pointer to the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) struture that describes this packet queue's net rings.

## -returns

Returns a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) that begins at the packet ring's **NextIndex** and ends at the packet ring's **EndIndex**. In other words, the iterator covers the packet ring's current post subsection.

## -remarks

Client drivers typically call this method to begin the process of posting packets to hardware. Drivers later complete this process by calling [**NetPacketIteratorSet**](../netringiterator/nf-netringiterator-netpacketiteratorset.md).

For an animation and code example of posting packets, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)

[**NetPacketIteratorSet**](../netringiterator/nf-netringiterator-netpacketiteratorset.md)
