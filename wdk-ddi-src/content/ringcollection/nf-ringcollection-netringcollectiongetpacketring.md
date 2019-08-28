---
UID: NF:ringcollection.NetRingCollectionGetPacketRing
title: NetRingCollectionGetPacketRing function (ringcollection.h)
description: The NetRingCollectionGetPacketRing gets the packet ring for a packet queue.
tech.root: netvista
ms.assetid: D4B33AEA-64FD-42F4-BADB-3CF9A1D0BBC6
ms.date: 02/06/2019
ms.topic: function
f1_keywords:
 - "ringcollection/RILWRITEPHONEBOOKENTRYPARAMS"
ms.keywords: NetRingCollectionGetPacketRing
req.header: ringcollection.h
req.include-header: netadaptercx.h
req.target-type: Universal
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
req.alt-api:
req.alt-loc:
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- ringcollection.h
apiname: 
- NetRingCollectionGetPacketRing
targetos: Windows
product:
- Windows
---

# NetRingCollectionGetPacketRing function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetRingCollectionGetPacketRing** gets the packet ring for a packet queue.

## -parameters

### -param Rings

A pointer to a [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure that describes this packet queue's net rings.

## -returns

Returns a pointer to the packet [**NET_RING**](../ring/ns-ring-_net_ring.md) for the packet queue.

## -remarks

Client drivers typically call this method when they need information about a packet ring, such as the number of elements in the ring. For example, during its queue initialization routines a client driver might need to allocate memory for hardware descriptors in a one-to-one ratio to the number of packets in the packet ring.

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)
