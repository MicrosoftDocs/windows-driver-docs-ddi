---
UID: NF:netringiterator.NetPacketIteratorAdvanceToTheEnd
title: NetPacketIteratorAdvanceToTheEnd function
author: windows-driver-content
description: The NetPacketIteratorAdvanceToTheEnd method advances the current Index of a packet iterator to its End index.
tech.root: netvista
ms.assetid: 4fcad121-2027-4bdb-9640-63b1dca2c4f6
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetPacketIteratorAdvanceToTheEnd"
ms.keywords: NetPacketIteratorAdvanceToTheEnd
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
- NetPacketIteratorAdvanceToTheEnd
product:
- Windows
targetos: Windows

---

# NetPacketIteratorAdvanceToTheEnd function


## -description



The **NetPacketIteratorAdvanceToTheEnd** method advances the current **Index** of a packet iterator to its **End** index.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) structure.

## -returns

None.

## -remarks

After calling **NetPacketIteratorAdvanceToTheEnd**, the packet iterator's current **Index** advances to the iterator's **End** index. Therefore, the packets between the old value of iterator's **Index** and the iterator's **End - 1** inclusive are transferred to the OS.

Client drivers typically call **NetPacketIteratorAdvanceToTheEnd** to cancel all packets in the ring or perform other operations that drain all the ring's packets.

For a code example of using this method, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)
