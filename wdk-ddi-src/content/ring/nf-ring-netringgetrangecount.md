---
UID: NF:ring.NetRingGetRangeCount
title: NetRingGetRangeCount function (ring.h)
description: Calculates the number of elements contained in a range of the specified net ring buffer.
tech.root: netvista
ms.assetid: 665010d3-f177-470c-a721-188c81a4cae7
ms.date: 01/31/2019
ms.topic: function
ms.keywords: NetRingGetRangeCount
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
-	NetRingGetRangeCount
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetRingGetRangeCount function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Calculates the number of elements contained in a range of the specified net ring buffer.

## -parameters

### -param RingBuffer
A pointer to a [**NET_RING**](../ring/ns-netring-_net_ring.md).

### -param StartIndex
The inclusive start of the range to measure.

### -param EndIndex
The exclusive end of the range to measure.

## -returns
The number of elements in the given range.

## -remarks
For example, consider a net ring containing a total of 8 elements. Index values for the elements are **0** through **7**. The number of elements in the range **[1, 4)** is 3. This is because the **EndIndex** value is not included, so the range includes elements at index values **1**, **2**, and **3**.

Similarly, the range **[4, 1)** includes elements at index values **4**, **5**, **6**, **7**, and **0** (looping back to the beginning of the ring), for a total of 5 elements.

Finally, note that an empty range like **[2, 2)** returns zero elements.

## -see-also
