---
UID: NF:ndis.NET_BUFFER_SHARED_MEM_FLAGS
title: NET_BUFFER_SHARED_MEM_FLAGS macro (ndis.h)
description: The NET_BUFFER_SHARED_MEM_FLAGS macro gets the shared memory flags from a NET_BUFFER_SHARED_MEMORY structure.
tech.root: netvista
ms.assetid: cf98dfad-0db3-414a-811a-61a29ee6fe15
ms.date: 04/13/2018
keywords: ["NET_BUFFER_SHARED_MEM_FLAGS macro"]
f1_keywords:
 - "ndis/NET_BUFFER_SHARED_MEM_FLAGS"
ms.keywords: NET_BUFFER_SHARED_MEM_FLAGS
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- NET_BUFFER_SHARED_MEM_FLAGS
product:
- Windows
targetos: Windows

---

# NET_BUFFER_SHARED_MEM_FLAGS macro


## -description

The **NET_BUFFER_SHARED_MEM_FLAGS** macro gets the shared memory flags from a [**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md) structure.

## -parameters

### -param _SHI

A pointer to a **NET_BUFFER_SHARED_MEMORY** structure.

## -returns

**NET_BUFFER_SHARED_MEM_FLAGS** returns a ULONG that contains shared memory flags.

## -remarks

An NDIS 6.20 or later driver can use the **NET_BUFFER_SHARED_MEM_FLAGS** macro to get shared memory flags that are associated with a [**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md) structure. **NET_BUFFER_SHARED_MEM_FLAGS** gets the flags from the **SharedMemoryFlags** member of the **NET_BUFFER_SHARED_MEMORY** structure. The **SharedMemoryInfo** member of the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure contains the first **NET_BUFFER_SHARED_MEMORY** structure in a linked list.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

[**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md)
