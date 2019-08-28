---
UID: NF:netringiterator.NetFragmentIteratorSet
title: NetFragmentIteratorSet function
author: windows-driver-content
description: The NetFragmentIteratorSet method completes a client driver's post or drain operation on the fragment ring.
tech.root: netvista
ms.assetid: 5f5e6e91-2b55-43cd-b088-ebc532012c74
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetFragmentIteratorSet"
ms.keywords: NetFragmentIteratorSet
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
- NetFragmentIteratorSet
product:
- Windows
targetos: Windows
---

# NetFragmentIteratorSet function


## -description



The **NetFragmentIteratorSet** method completes a client driver's post or drain operation on the fragment ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) structure.

## -returns

None.

## -remarks

**NetFragmentIteratorSet** sets the fragment iterator's **IndexToSet** to its **Index**, which indicates to the OS that the client driver has finished processing the fragments from **IndexToSet** to **Index - 1** inclusive. Client drivers call this method to finish posting fragments to hardware, or to finish draining fragments to the OS.

For an animation and code example of draining fragments back to the OS, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)
