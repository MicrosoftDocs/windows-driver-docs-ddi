---
UID: NF:netringiterator.NetRingGetDrainPackets
title: NetRingGetDrainPackets function
author: windows-driver-content
description: The NetRingGetDrainPackets method gets a packet iterator for the drain subsection of a packet ring.
tech.root: netvista
ms.assetid: 0181ab7c-9f8e-43f3-b2c4-f8e601109c6e
ms.author: windowsdriverdev
ms.date: 02/01/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetRingGetDrainPackets"
ms.keywords: NetRingGetDrainPackets
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
- NetRingGetDrainPackets
product:
- Windows
targetos: Windows
---

# NetRingGetDrainPackets function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetRingGetDrainPackets** method gets a packet iterator for the drain subsection of a packet ring.

## -parameters

### -param Rings

A pointer to the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) struture that describes this packet queue's net rings.

## -returns

Returns a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) that begins at the packet ring's **BeginIndex** and ends at the packet ring's **NextIndex**. In other words, the iterator covers the packet ring's current drain subsection.

## -remarks

Client drivers typically call this method to begin the process of draining packets from the packet ring to the OS. Drivers later complete this process by calling [**NetPacketIteratorSet**](../netringiterator/nf-netringiterator-netpacketiteratorset.md).

For an animation and code example of posting packets, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)

[**NetPacketIteratorSet**](../netringiterator/nf-netringiterator-netpacketiteratorset.md)
