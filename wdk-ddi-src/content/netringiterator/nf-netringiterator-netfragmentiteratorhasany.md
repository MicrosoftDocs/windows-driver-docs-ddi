---
UID: NF:netringiterator.NetFragmentIteratorHasAny
title: NetFragmentIteratorHasAny function
author: windows-driver-content
description: The NetFragmentIteratorHasAny method determines whether a fragment iterator has any valid elements to process in the fragment ring.
tech.root: netvista
ms.assetid: 852f310d-e346-49c3-8648-639fb817b70e
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetFragmentIteratorHasAny"
ms.keywords: NetFragmentIteratorHasAny
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
- NetFragmentIteratorHasAny
product:
- Windows
targetos: Windows
---

# NetFragmentIteratorHasAny function


## -description



The **NetFragmentIteratorHasAny** method determines whether a fragment iterator has any valid elements to process in the fragment ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) structure.

## -returns

Returns **TRUE** if the iterator's **Index** does not equal its **End** index. In other words, the iterator has a fragment to process. Otherwise, returns **FALSE**.

## -remarks

Client drivers can call **NetFragmentIteratorHasAny** to test if the iterator has any valid elements to process. This method can be used to verify a fragment before processing it, or it can be used as a test condition for a loop when the driver is processing multiple fragments in a batch.

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)
