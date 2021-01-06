---
UID: NF:ring.NetRingGetRangeCount
title: NetRingGetRangeCount function (ring.h)
description: Calculates the number of elements contained in a range of the specified net ring buffer.
tech.root: netvista
ms.date: 01/31/2019
keywords: ["NetRingGetRangeCount function"]
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
targetos: Windows
f1_keywords:
 - NetRingGetRangeCount
 - ring/NetRingGetRangeCount
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ring.h
api_name:
 - NetRingGetRangeCount
---

# NetRingGetRangeCount function


## -description

Calculates the number of elements contained in a range of the specified net ring buffer.

## -parameters

### -param RingBuffer

A pointer to a [**NET_RING**](../ring/ns-ring-_net_ring.md).

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

