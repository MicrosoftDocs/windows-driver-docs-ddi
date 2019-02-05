---
UID: NF:netringiterator.NetPacketIteratorHasAny
title: NetPacketIteratorHasAny function
author: windows-driver-content
description: The NetPacketIteratorHasAny method determines whether a packet iterator has any valid elements to process in the packet ring.
tech.root: netvista
ms.assetid: 117bd7cc-deff-44f9-b5bf-f9b69353b636
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
ms.keywords: NetPacketIteratorHasAny
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
- NetPacketIteratorHasAny
product: Windows
targetos: Windows

---

# NetPacketIteratorHasAny function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetPacketIteratorHasAny** method determines whether a packet iterator has any valid elements to process in the packet ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) structure.

## -returns

Returns **TRUE** if the iterator's **Index** does not equal its **End** index. In other words, the iterator has a packet to process. Otherwise, returns **FALSE**.

## -remarks

Client drivers can call **NetPacketIteratorHasAny** to test if the iterator has any valid elements to process. This method can be used to verify a packet before processing it, or it can be used as a test condition for a loop when the driver is processing multiple packets in a batch.

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)