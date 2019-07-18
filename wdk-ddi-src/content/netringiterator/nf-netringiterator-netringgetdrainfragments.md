---
UID: NF:netringiterator.NetRingGetDrainFragments
title: NetRingGetDrainFragments function
author: windows-driver-content
description: The NetRingGetDrainFragments method gets a fragment iterator for the current drain subsection of a fragment ring.
tech.root: netvista
ms.assetid: 881ad7f6-1d87-4c4d-bc80-acae45446c56
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetRingGetDrainFragments"
ms.keywords: NetRingGetDrainFragments
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
- NetRingGetDrainFragments
product: Windows
targetos: Windows

---

# NetRingGetDrainFragments function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetRingGetDrainFragments** method gets a fragment iterator for the current drain subsection of a fragment ring.

## -parameters

### -param Rings

A pointer to the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) struture that describes the packet queue's net rings.

## -returns

Returns a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) that begins at the fragment ring's **BeginIndex** and ends at the fragment ring's **NextIndex**. In other words, the iterator covers the fragment ring's current drain section.

## -remarks

Client drivers call **NetRingGetDrainFragments** to begin the process of draining receive (Rx) fragments from the ring to the OS.

For an animation and code example of draining fragments from the ring back to the OS, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)

[**NetFragmentIteratorSet**](../netringiterator/nf-netringiterator-netfragmentiteratorset.md)
