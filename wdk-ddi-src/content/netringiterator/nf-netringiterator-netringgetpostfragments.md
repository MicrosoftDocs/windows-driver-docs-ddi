---
UID: NF:netringiterator.NetRingGetPostFragments
title: NetRingGetPostFragments function
author: windows-driver-content
description: The NetRingGetPostFragments method gets a fragment iterator for the current post subsection of a fragment ring.
tech.root: netvista
ms.assetid: e2897dbe-c9f3-4d35-b704-4c230681c879
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
ms.keywords: NetRingGetPostFragments
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
- NetRingGetPostFragments
product: Windows
targetos: Windows

---

# NetRingGetPostFragments function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetRingGetPostFragments** method gets a fragment iterator for the current post subsection of a fragment ring.

## -parameters

### -param Rings

A pointer to the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) struture that describes the packet queue's net rings.

## -returns

Returns a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) that begins at the fragment ring's **NextIndex** and ends at the fragment ring's **EndIndex**. In other words, the iterator covers the fragment ring's current post subsection.

## -remarks

Client drivers typically call **NetRingGetPostFragments** to begin the process of posting fragments to hardware for receiving (Rx). Drivers later complete this process by calling [**NetFragmentIteratorSet**](../netringiterator/nf-netringiterator-netfragmentiteratorset.md).

For an animation and code example of posting fragments to hardware for Rx, see Net rings and net ring iterators.

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)

[**NetFragmentIteratorSet**](../netringiterator/nf-netringiterator-netfragmentiteratorset.md)