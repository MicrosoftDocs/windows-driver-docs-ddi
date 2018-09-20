---
UID: NF:ndis.NET_BUFFER_LIST_CONTEXT_DATA_SIZE
title: NET_BUFFER_LIST_CONTEXT_DATA_SIZE macro
author: windows-driver-content
description: NET_BUFFER_LIST_CONTEXT_DATA_SIZE is a macro that NDIS drivers use to get the size of the NET_BUFFER_LIST_CONTEXT data buffer that is associated with a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: a82d45f6-fd89-4cb3-9a43-2dcb25a0690b
ms.author: windowsdriverdev
ms.date: 04/12/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_CONTEXT_DATA_SIZE
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
-	NET_BUFFER_LIST_CONTEXT_DATA_SIZE
product:
-	Windows
targetos: Windows

---

# NET_BUFFER_LIST_CONTEXT_DATA_SIZE macro


## -description

**NET_BUFFER_LIST_CONTEXT_DATA_SIZE** is a macro that NDIS drivers use to get the size of the [**NET_BUFFER_LIST_CONTEXT**](ns-ndis-_net_buffer_list_context.md) data buffer that is associated with a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_CONTEXT_DATA_SIZE** returns the size, in bytes, of the **NET_BUFFER_LIST_CONTEXT** data buffer that is associated with the indicated [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -remarks

**NET_BUFFER_LIST_CONTEXT_DATA_SIZE** gets the return value from the **Size** member of the first [**NET_BUFFER_LIST_CONTEXT**](ns-ndis-_net_buffer_list_context.md) structure.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

[**NET_BUFFER_LIST_CONTEXT**](ns-ndis-_net_buffer_list_context.md)
