---
UID: NF:ring.NetRingGetElementAtIndex
title: NetRingGetElementAtIndex function (ring.h)
description: The NetRingGetElementAtIndex function retrieves an element from a net ring.
tech.root: netvista
ms.assetid: 5feeac1c-9c69-4179-8604-5aaaff7e60a0
ms.date: 09/25/2019
keywords: ["NetRingGetElementAtIndex function"]
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
targetos: Windows
f1_keywords:
 - NetRingGetElementAtIndex
 - ring/NetRingGetElementAtIndex
topictype:
 - apiref
apitype:
 - HeaderDef
apilocation:
 - ring.h
apiname:
 - NetRingGetElementAtIndex
---

# NetRingGetElementAtIndex function


## -description

The **NetRingGetElementAtIndex** function retrieves an element from a net ring.

## -parameters

### -param Ring

A pointer to a [**NET_RING**](../ring/ns-ring-_net_ring.md).

### -param Index

The element index, within the range **[0, Ring->NumberOfElements)**.

## -returns

Returns the element at the specified location.

## -remarks

**NetRingGetElementAtIndex** uses the **ElementStride** member of the net ring to index into the buffer and returns the location of the specified element.

**NetRingGetElementAtIndex** is meant for generic use of net rings. Instead, a NetAdapterCx client driver typically calls either [**NetRingGetPacketAtIndex**](../ring/nf-ring-netringgetpacketatindex.md) for a packet ring or [**NetRingGetFragmentAtIndex**](../ring/nf-ring-netringgetfragmentatindex.md) for a fragment ring.

## -see-also

[**NetRingGetPacketAtIndex**](../ring/nf-ring-netringgetpacketatindex.md)

[**NetRingGetFragmentAtIndex**](../ring/nf-ring-netringgetfragmentatindex.md)

