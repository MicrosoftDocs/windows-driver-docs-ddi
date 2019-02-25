---
UID: NF:netringiterator.NetFragmentIteratorAdvanceToTheEnd
title: NetFragmentIteratorAdvanceToTheEnd function
author: windows-driver-content
description: The NetFragmentIteratorAdvanceToTheEnd method advances the current Index of a fragment iterator to its End index.
tech.root: netvista
ms.assetid: fbeac06a-4274-43c9-bcef-c9672c0105b9
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
ms.keywords: NetFragmentIteratorAdvanceToTheEnd
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
- NetFragmentIteratorAdvanceToTheEnd
product: Windows
targetos: Windows
---

# NetFragmentIteratorAdvanceToTheEnd function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetFragmentIteratorAdvanceToTheEnd** method advances the current **Index** of a fragment iterator to its **End** index.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) structure.

## -returns

None.

## -remarks

After calling **NetFragmentIteratorAdvanceToTheEnd**, the fragment iterator's current **Index** advances to the iterator's **End** index. Therefore, the fragments between the old value of iterator's **Index** and the iterator's **End - 1** inclusive are transferred to the OS.

Client drivers typically call **NetFragmentIteratorAdvanceToTheEnd** to cancel all fragments in the ring or perform other operations that drain all the ring's fragments.

For a code example of using this method, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)