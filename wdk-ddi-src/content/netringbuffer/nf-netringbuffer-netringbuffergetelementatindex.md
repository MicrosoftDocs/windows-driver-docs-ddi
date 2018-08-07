---
UID: NF:netringbuffer.NetRingBufferGetElementAtIndex
title: NetRingBufferGetElementAtIndex function
author: windows-driver-content
description: Returns the element at the specified index in the ring buffer.
ms.assetid: 5feeac1c-9c69-4179-8604-5aaaff7e60a0
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRingBufferGetElementAtIndex
req.header: netringbuffer.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
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
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netringbuffer.h
apiname: 
-	NetRingBufferGetElementAtIndex
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRingBufferGetElementAtIndex function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Returns the element at the specified index in the ring buffer.

## -parameters

### -param RingBuffer
A pointer to a [NET_RING_BUFFER](ns-netringbuffer-_net_ring_buffer.md).

### -param Index
The element index, within the range [0, RingBuffer->NumberOfElements).

## -returns
Returns the location of the specified element.

## -remarks
**NetRingBufferGetElementAtIndex** uses the **ElementStride** member of the ring buffer to index into the buffer and returns the location of the specified element.

You'll need to cast the returned element to whatever data type your ring buffer elements use.

**NetRingBufferGetElementAtIndex** is meant for generic use of ring buffers. Instead, a NetAdapterCx client driver typically calls [NetRingBufferGetPacketAtIndex](../netadapterpacket/nf-netadapterpacket-netringbuffergetpacketatindex.md).

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).



## -see-also