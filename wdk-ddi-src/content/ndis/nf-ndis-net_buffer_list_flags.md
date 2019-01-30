---
UID: NF:ndis.NET_BUFFER_LIST_FLAGS
title: NET_BUFFER_LIST_FLAGS macro (ndis.h)
description: NET_BUFFER_LIST_FLAGS is a macro that NDIS drivers use to get the flags associated with a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: dbfc432b-5751-4796-8ede-2d9e73759e3b
ms.date: 04/12/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_FLAGS
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndis.h
api_name: 
-	NET_BUFFER_LIST_FLAGS
product:
-	Windows
targetos: Windows

---

# NET_BUFFER_LIST_FLAGS macro


## -description

**NET_BUFFER_LIST_FLAGS** is a macro that NDIS drivers use to get the flags associated with a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_FLAGS** returns the **Flags** member of the indicated **NET_BUFFER_LIST** structure.

## -remarks

For definitions of possible **NET_BUFFER_LIST** structure flags, see [**NDIS_BUFFER_LIST**](ns-ndis-_net_buffer_list.md).

## -see-also

[**NDIS_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
