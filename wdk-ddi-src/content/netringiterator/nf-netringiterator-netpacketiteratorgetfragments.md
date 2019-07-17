---
UID: NF:netringiterator.NetPacketIteratorGetFragments
title: NetPacketIteratorGetFragments function
author: windows-driver-content
description: The NetPacketIteratorGetFragments method gets the fragments associated with a packet.
tech.root: netvista
ms.assetid: 7f9acdb6-d645-4cd8-82cf-8ac61ec972fc
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetPacketIteratorGetFragments"
ms.keywords: NetPacketIteratorGetFragments
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
- NetPacketIteratorGetFragments
product: Windows
targetos: Windows

---

# NetPacketIteratorGetFragments function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetPacketIteratorGetFragments** method gets the fragments associated with a packet.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) structure.

## -returns

Returns a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) that begins at the first fragment belonging to this packet and ends at the last fragment belonging to this packet.

## -remarks

Client drivers typically call NetPacketIteratorGetFragments to begin the process of posting fragments to hardware for transmitting (Tx).
For an animation and code example of posting fragments to hardware for Tx, see Net rings and net ring iterators.

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)
