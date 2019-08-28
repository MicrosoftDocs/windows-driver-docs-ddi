---
UID: NF:netringiterator.NetPacketIteratorGetIndex
title: NetPacketIteratorGetIndex function
author: windows-driver-content
description: The NetPacketIteratorGetIndex method gets the current Index of a packet iterator in the packet ring.
tech.root: netvista
ms.assetid: d9818195-af1c-4c80-b018-ede991ef2860
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetPacketIteratorGetIndex"
ms.keywords: NetPacketIteratorGetIndex
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
- NetPacketIteratorGetIndex
product:
- Windows
targetos: Windows
---

# NetPacketIteratorGetIndex function


## -description



The **NetPacketIteratorGetIndex** method gets the current **Index** of a packet iterator in the packet ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) structure.

## -returns

Returns the packet iterator's current **Index**.

## -remarks

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)
