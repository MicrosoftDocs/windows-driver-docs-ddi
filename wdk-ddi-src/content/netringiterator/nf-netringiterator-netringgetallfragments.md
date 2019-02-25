---
UID: NF:netringiterator.NetRingGetAllFragments
title: NetRingGetAllFragments function
author: windows-driver-content
description: The NetRingGetAllFragments method gets a fragment iterator for the entire range that a client driver owns in a fragment ring.
tech.root: netvista
ms.assetid: c47d6552-9068-44c3-814e-989d46e73ac4
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
ms.keywords: NetRingGetAllFragments
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
- NetRingGetAllFragments
product: Windows
targetos: Windows

---

# NetRingGetAllFragments function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetRingGetAllFragments** method gets a fragment iterator for the entire range that a client driver owns in a fragment ring.

## -parameters

### -param Rings

A pointer to the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) struture that describes the packet queue's net rings.

## -returns

Returns a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) that begins at the fragment ring's **BeginIndex** and ends at the fragment ring's **EndIndex**. In other words, the iterator covers both the ring's post subsection and its drain subsection, or all fragments in the ring that the driver currently owns.

## -remarks

Client drivers typically call **NetRingGetAllFragments** to begin performing operations on all fragments that they own in a fragment ring. This might include processing a batch of receives that span all available fragments in the ring, or draining the ring during data path cancellation.

For a code example of using this method, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)