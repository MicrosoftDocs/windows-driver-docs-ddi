---
UID: NF:netringiterator.NetPacketIteratorSet
title: NetPacketIteratorSet function
author: windows-driver-content
description: The NetPacketIteratorSet method completes a client driver's post or drain operation on the packet ring.
tech.root: netvista
ms.assetid: 640e0117-31c2-404d-9de9-027dff164e60
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
ms.keywords: NetPacketIteratorSet
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
- NetPacketIteratorSet
product: Windows
targetos: Windows

---

# NetPacketIteratorSet function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetPacketIteratorSet** method completes a client driver's post or drain operation on the packet ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) structure.

## -returns

None.

## -remarks

**NetPacketIteratorSet** sets the packet iterator's **IndexToSet** to its **Index**, which indicates to the OS that the client driver has finished processing the packets from **IndexToSet** to **Index - 1** inclusive. Client drivers call this method to finish posting packets to hardware, or to finish draining packets to the OS.

For an animation and code example of draining packets back to the OS, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)