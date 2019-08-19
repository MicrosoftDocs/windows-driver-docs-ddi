---
UID: NF:netringiterator.NetPacketIteratorGetCount
title: NetPacketIteratorGetCount function
author: windows-driver-content
description: The NetPacketIteratorGetCount method gets the count of packets that a client driver owns in the packet ring.
tech.root: netvista
ms.assetid: 95c6bc74-0188-4b7f-99ee-4c6c7e9eeb66
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetPacketIteratorGetCount"
ms.keywords: NetPacketIteratorGetCount
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
- NetPacketIteratorGetCount
product:
- Windows
targetos: Windows

---

# NetPacketIteratorGetCount function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetPacketIteratorGetCount** method gets the count of packets that a client driver owns in the packet ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) structure.

## -returns

Returns the number of packets between this packet iterator's current **Index** and **EndIndex - 1** inclusive. For example, if the iterator's **Index** is **1** and its **End** index is **5**, the client driver owns four packets: **1**, **2**, **3**, and **4**.

## -remarks

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)
