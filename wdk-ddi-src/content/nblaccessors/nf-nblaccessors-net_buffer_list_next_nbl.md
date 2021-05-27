---
UID: NF:nblaccessors.NET_BUFFER_LIST_NEXT_NBL
title: NET_BUFFER_LIST_NEXT_NBL
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: NET_BUFFER_LIST_NEXT_NBL is a macro that NDIS drivers use to get the next NET_BUFFER_LIST structure in a linked list of NET_BUFFER_LIST structures.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/nblaccessors.h
req.idl: 
req.include-header: ndis.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nblaccessors.h
api_name:
 - NET_BUFFER_LIST_NEXT_NBL
f1_keywords:
 - NET_BUFFER_LIST_NEXT_NBL
 - nblaccessors/NET_BUFFER_LIST_NEXT_NBL
dev_langs:
 - c++
---

# NET_BUFFER_LIST_NEXT_NBL macro


## -description

**NET_BUFFER_LIST_NEXT_NBL** is a macro that NDIS drivers use to get the next [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure in a linked list of **NET_BUFFER_LIST** structures.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_NEXT_NBL** returns a pointer to the next [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure in the linked list of **NET_BUFFER_LIST** structures, or it returns **NULL** if the end of the linked list is reached.

## -remarks

**NET_BUFFER_LIST_NEXT_NBL** gets the return value from the **Next** member of the [**NET_BUFFER_LIST_DATA**](ns-ndis-_net_buffer_list_data.md) structure in the [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure that the *\_NBL* parameter points to.

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

[**NET_BUFFER_LIST_DATA**](ns-ndis-_net_buffer_list_data.md)


