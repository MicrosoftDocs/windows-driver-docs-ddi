---
UID: NF:netringiterator.NetFragmentIteratorGetCount
title: NetFragmentIteratorGetCount function
author: windows-driver-content
description: The NetFragmentIteratorGetCount method gets the count of fragments that a client driver owns in the fragment ring.
tech.root: netvista
ms.assetid: 3be60cc3-78a8-4c97-91c7-796868da6465
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
ms.keywords: NetFragmentIteratorGetCount
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
- NetFragmentIteratorGetCount
product: Windows
targetos: Windows
---

# NetFragmentIteratorGetCount function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetFragmentIteratorGetCount** method gets the count of fragments that a client driver owns in the fragment ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) structure.

## -returns

Returns the number of fragments between this fragment iterator's current **Index** and **EndIndex - 1** inclusive. For example, if the iterator's **Index** is **1** and its **End** index is **5**, the client driver owns four fragments: **1**, **2**, **3**, and **4**.

## -remarks

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)