---
UID: NF:ring.NetRingGetFragmentAtIndex
title: NetRingGetFragmentAtIndex function (ring.h)
author: windows-driver-content
description: The NetRingGetFragmentAtIndex method retrieves a fragment from a net ring.
tech.root: netvista
ms.assetid: 4cd64469-7623-437b-b85d-3fd5535495be
ms.author: windowsdriverdev
ms.date: 09/25/2019
keywords: ["NetRingGetFragmentAtIndex function"]
f1_keywords:
 - "ring/NetRingGetFragmentAtIndex"
 - "NetRingGetFragmentAtIndex"
ms.keywords: NetRingGetFragmentAtIndex
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ring.h
api_name: 
- NetRingGetFragmentAtIndex
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetRingGetFragmentAtIndex function

## -description

The **NetRingGetFragmentAtIndex** method retrieves a fragment from a net ring.

## -parameters

### -param Ring

A pointer to a [**NET_RING**](../ring/ns-ring-_net_ring.md).

### -param Index

The fragment index, within the range **[0, Ring->NumberOfElements)**.

## -returns

Returns a pointer to the [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) at the specified index in the fragment ring.

## -remarks

This method is a convenient wrapper around [**NetRingGetElementAtIndex**](../ring/nf-ring-netringgetelementatindex.md). Client drivers should call this method when working with a fragment ring instead of calling **NetRingGetElementAtIndex** directly.

## -see-also

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NetRingGetElementAtIndex**](../ring/nf-ring-netringgetelementatindex.md)
