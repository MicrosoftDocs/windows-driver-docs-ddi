---
UID: NF:netringiterator.NetPacketIteratorAdvance
title: NetPacketIteratorAdvance function
author: windows-driver-content
description: The NetPacketIteratorAdvance method advances the Index of a packet iterator by one.
tech.root: netvista
ms.assetid: dc7058ef-5242-4959-aa33-cf04ffcbfe48
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
ms.keywords: NetPacketIteratorAdvance
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
- NetPacketIteratorAdvance
product: Windows
targetos: Windows

---

# NetPacketIteratorAdvance function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetPacketIteratorAdvance** method advances the **Index** of a packet iterator by one.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) structure.

## -returns

None.

## -remarks

If the packet iterator's current **Index** is at the end of the packet ring, this method automatically handles wrapping around to the beginning of the ring.

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)