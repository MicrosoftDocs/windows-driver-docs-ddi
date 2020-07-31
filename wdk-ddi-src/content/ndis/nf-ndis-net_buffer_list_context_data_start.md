---
UID: NF:ndis.NET_BUFFER_LIST_CONTEXT_DATA_START
title: NET_BUFFER_LIST_CONTEXT_DATA_START macro (ndis.h)
description: NET_BUFFER_LIST_CONTEXT_DATA_START is a macro that NDIS drivers use to get a pointer to the NET_BUFFER_LIST_CONTEXT context space that is associated with a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 138860cc-9b85-4772-9a99-cb0de66e4bdb
ms.date: 04/12/2018
keywords: ["NET_BUFFER_LIST_CONTEXT_DATA_START macro"]
f1_keywords:
 - "ndis/NET_BUFFER_LIST_CONTEXT_DATA_START"
 - "NET_BUFFER_LIST_CONTEXT_DATA_START"
ms.keywords: NET_BUFFER_LIST_CONTEXT_DATA_START
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
- apiref
api_type: 
- HeaderDef
api_location: 
- ndis.h
api_name: 
- NET_BUFFER_LIST_CONTEXT_DATA_START
targetos: Windows

---

# NET_BUFFER_LIST_CONTEXT_DATA_START macro


## -description

**NET_BUFFER_LIST_CONTEXT_DATA_START** is a macro that NDIS drivers use to get a pointer to the [**NET_BUFFER_LIST_CONTEXT**](ns-ndis-_net_buffer_list_context.md) context space that is associated with a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_CONTEXT_DATA_START** returns a pointer to the **NET_BUFFER_LIST_CONTEXT** context space that is associated with the indicated [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -remarks

**NET_BUFFER_LIST_CONTEXT_DATA_START** returns a pointer to the start of the *used context space* in the **ContextData** member of the [**NET_BUFFER_LIST_CONTEXT**](ns-ndis-_net_buffer_list_context.md) structure.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

[**NET_BUFFER_LIST_CONTEXT**](ns-ndis-_net_buffer_list_context.md)
