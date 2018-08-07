---
UID: NF:netringbuffer.NetRingBufferIncrementIndex
title: NetRingBufferIncrementIndex function
author: windows-driver-content
description: Returns the next index value after the specified index value, wrapping around to the beginning of the ring buffer if necessary.
ms.assetid: c17368bb-9abd-4d02-a94b-76dfdc344b54
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRingBufferIncrementIndex
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
-	NetRingBufferIncrementIndex
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRingBufferIncrementIndex function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Returns the next index value after the specified index value, wrapping around to the beginning of the ring buffer if necessary.

## -parameters

### -param RingBuffer
A pointer to a [NET_RING_BUFFER](ns-netringbuffer-_net_ring_buffer.md).

### -param Index
The index value to increment.

## -returns
Returns the next index value after the specified index value, wrapping around to the beginning of the ring buffer if necessary.

## -remarks
This routine is equivalent to `Index++`, except it accounts for the wraparound of a ring buffer.

For example, you can use this routine to return a packet to the operating system by incrementing **BeginIndex**:

```c++
NET_RING_BUFFER *ringBuffer = . . .;
ringBuffer->BeginIndex = NetRingBufferIncrementIndex(ringBuffer, ringBuffer->BeginIndex);
```



## -see-also