---
UID: NF:ring.NetRingGetElementAtIndex
title: NetRingGetElementAtIndex function (ring.h)
description: Returns the element at the specified index in the net ring.
tech.root: netvista
ms.assetid: 5feeac1c-9c69-4179-8604-5aaaff7e60a0
ms.date: 01/31/2019
ms.topic: function
f1_keywords:
 - "ring/RILWRITEPHONEBOOKENTRYPARAMS"
ms.keywords: NetRingGetElementAtIndex
req.header: ring.h
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
- ring.h
apiname: 
- NetRingGetElementAtIndex
targetos: Windows
product:
- Windows
---

# NetRingGetElementAtIndex function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Returns the element at the specified index in the net ring.

## -parameters

### -param RingBuffer
A pointer to a [**NET_RING**](../ring/ns-netring-_net_ring.md).

### -param Index
The element index, within the range **[0, RingBuffer->NumberOfElements)**.

## -returns
Returns the location of the specified element.

## -remarks
**NetRingGetElementAtIndex** uses the **ElementStride** member of the net ring to index into the buffer and returns the location of the specified element.

You'll need to cast the returned element to whatever data type your net ring elements use.

**NetRingGetElementAtIndex** is meant for generic use of net rings. Instead, a NetAdapterCx client driver typically use net ring iterators to get a packet with the [**NetPacketIteratorGetPacket**](../netringiterator/nf-netringiterator-netpacketiteratorgetpacket.md).

For more info, see [Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators).

## -see-also
