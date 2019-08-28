---
UID: NF:netringiterator.NetFragmentIteratorGetIndex
title: NetFragmentIteratorGetIndex function
author: windows-driver-content
description: The NetFragmentIteratorGetIndex method gets the current Index of a fragment iterator in the fragment ring.
tech.root: netvista
ms.assetid: c949cb18-cab0-4a53-8d2a-b6af38b9b095
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetFragmentIteratorGetIndex"
ms.keywords: NetFragmentIteratorGetIndex
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
- NetFragmentIteratorGetIndex
product:
- Windows
targetos: Windows

---

# NetFragmentIteratorGetIndex function


## -description



The **NetFragmentIteratorGetIndex** method gets the current **Index** of a fragment iterator in the fragment ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) structure.

## -returns

Returns the fragment iterator's current **Index**.

## -remarks

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)
