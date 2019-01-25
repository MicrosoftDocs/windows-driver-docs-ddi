---
UID: NF:ndis.NET_BUFFER_LIST_NEXT_NBL
title: NET_BUFFER_LIST_NEXT_NBL macro (ndis.h)
description: NET_BUFFER_LIST_NEXT_NBL is a macro that NDIS drivers use to get the next NET_BUFFER_LIST structure in a linked list of NET_BUFFER_LIST structures.
tech.root: netvista
ms.assetid: 43a4a7df-a62e-4192-b2b5-2ae64698177c
ms.date: 04/13/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_NEXT_NBL
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
-	NET_BUFFER_LIST_NEXT_NBL
product:
-	Windows
targetos: Windows

---

# NET_BUFFER_LIST_NEXT_NBL macro


## -description

**NET_BUFFER_LIST_NEXT_NBL** is a macro that NDIS drivers use to get the next [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure in a linked list of **NET_BUFFER_LIST** structures.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_NEXT_NBL** returns a pointer to the next [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure in the linked list of **NET_BUFFER_LIST** structures, or it returns **NULL** if the end of the linked list is reached.

## -remarks

**NET_BUFFER_LIST_NEXT_NBL** gets the return value from the **Next** member of the [**NET_BUFFER_LIST_DATA**](ns-ndis-_net_buffer_list_data.md) structure in the [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure that the *\_NBL* parameter points to.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

[**NET_BUFFER_LIST_DATA**](ns-ndis-_net_buffer_list_data.md)
