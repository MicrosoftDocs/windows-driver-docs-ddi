---
UID: NF:netringiterator.NetFragmentIteratorGetFragment
title: NetFragmentIteratorGetFragment function
author: windows-driver-content
description: The NetFragmentIteratorGetFragment method gets the NET_FRAGMENT structure at a fragment iterator's current Index in the fragment ring.
tech.root: netvista
ms.assetid: 7ae806b5-55ae-4f4f-881a-82aaf3f4975d
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetFragmentIteratorGetFragment"
ms.keywords: NetFragmentIteratorGetFragment
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
- NetFragmentIteratorGetFragment
product: Windows
targetos: Windows

---

# NetFragmentIteratorGetFragment function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetFragmentIteratorGetFragment** method gets the [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) structure at a fragment iterator's current **Index** in the fragment ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) structure.

## -returns

Returns a pointer to the [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) structure at the fragment iterator's **Index**.

## -remarks

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)
