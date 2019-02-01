---
UID: NF:ring.NetRingIncrementIndex
title: NetRingIncrementIndex function (ring.h)
description: Returns the next index value after the specified index value, wrapping around to the beginning of the ring buffer if necessary.
tech.root: netvista
ms.assetid: c17368bb-9abd-4d02-a94b-76dfdc344b54
ms.date: 01/32/2019
ms.topic: function
ms.keywords: NetRingIncrementIndex
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
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	ring.h
apiname: 
-	NetRingIncrementIndex
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetRingIncrementIndex function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Returns the next index value after the specified index value, wrapping around to the beginning of the ring buffer if necessary.

## -parameters

### -param RingBuffer
A pointer to a [**NET_RING**](../ring/ns-netring-_net_ring.md).

### -param Index
The index value to increment.

## -returns
Returns the next index value after the specified index value, wrapping around to the beginning of the ring buffer if necessary.

## -remarks
This routine is equivalent to `Index++`, except it accounts for the wraparound of a ring buffer.

## -see-also
