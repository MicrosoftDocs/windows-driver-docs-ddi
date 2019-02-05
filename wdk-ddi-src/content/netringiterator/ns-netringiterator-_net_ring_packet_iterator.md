---
UID: NS:netringiterator._NET_RING_PACKET_ITERATOR
title: NET_RING_PACKET_ITERATOR
author: windows-driver-content
description: A NET_RING_PACKET_ITERATOR is a wrapper around a NET_RING_ITERATOR that client drivers use for net packet rings.
tech.root: netvista
ms.assetid: 1b446923-9932-4797-9744-bde6474b8235
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: struct
ms.keywords: NET_RING_PACKET_ITERATOR, NET_RING_PACKET_ITERATOR, 
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
req.typenames: NET_RING_PACKET_ITERATOR
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - netringiterator.h
api_name: 
 - NET_RING_PACKET_ITERATOR
product: Windows
targetos: Windows
---

# NET_RING_PACKET_ITERATOR structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

A **NET_RING_PACKET_ITERATOR** is a wrapper around a [**NET_RING_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_iterator.md) that client drivers use for net packet rings.

## -struct-fields

### -field Iterator

The [**NET_RING_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_iterator.md) structure around which this structure wraps. 

## -remarks

For packet rings, client drivers must use a **NET_RING_PACKET_ITERATOR** instead of using a [**NET_RING_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_iterator.md) directly.

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_iterator.md)