---
UID: NF:ring.NetRingAdvanceIndex
title: NetRingAdvanceIndex function (ring.h)
description: The NetRingAdvanceIndex function advances the index in a net ring forward, wrapping around if necessary.
tech.root: netvista
ms.date: 09/25/2019
keywords: ["NetRingAdvanceIndex function"]
ms.keywords: NetRingAdvanceIndex
req.header: ring.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NetRingAdvanceIndex
 - ring/NetRingAdvanceIndex
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ring.h
api_name:
 - NetRingAdvanceIndex
product:
 - Windows
---

# NetRingAdvanceIndex function


## -description

The **NetRingAdvanceIndex** function advances the index in a net ring forward, wrapping around if necessary.

## -parameters

### -param Ring

A pointer to a [**NET_RING**](../ring/ns-ring-_net_ring.md) to access.

### -param Index

The index value to advance.

### -param Distance

The distance to advance the index.

## -returns

Returns the new index after advancing **Distance** forward in the net ring.

## -remarks

**NetRingAdvanceIndex** enables client drivers to move forward multiple indices in the net ring. Client drivers can also call the wrapper function [**NetRingIncrementIndex**](../ring/nf-ring-netringincrementindex.md) to increment the index by **1**.

## -see-also

[**NET_RING**](../ring/ns-ring-_net_ring.md)

[**NetRingIncrementIndex**](../ring/nf-ring-netringincrementindex.md)

