---
UID: NF:ndis.NET_BUFFER_SHARED_MEM_NEXT_SEGMENT
title: NET_BUFFER_SHARED_MEM_NEXT_SEGMENT macro
author: windows-driver-content
description: The NET_BUFFER_SHARED_MEM_NEXT_SEGMENT macro gets the next shared memory segment from a NET_BUFFER_SHARED_MEMORY structure.
ms.assetid: 8576525d-ec6f-4986-924e-8550b47a0ba3
ms.author: windowsdriverdev
ms.date: 04/13/2018
ms.topic: macro
ms.keywords: NET_BUFFER_SHARED_MEM_NEXT_SEGMENT
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
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndis.h
api_name: 
-	NET_BUFFER_SHARED_MEM_NEXT_SEGMENT
product:
-	Windows
targetos: Windows

---

# NET_BUFFER_SHARED_MEM_NEXT_SEGMENT macro


## -description

The **NET_BUFFER_SHARED_MEM_NEXT_SEGMENT** macro gets the next shared memory segment from a [**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md) structure.

## -parameters

### -param _SHI

A pointer to a **NET_BUFFER_SHARED_MEMORY** structure.

## -returns

**NET_BUFFER_SHARED_MEM_NEXT_SEGMENT** returns a pointer to a [**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md) structure or returns **NULL**.

## -remarks

An NDIS 6.20 or later driver can use the **NET_BUFFER_SHARED_MEM_NEXT_SEGMENT** macro to get the next shared memory segment in a linked list of [**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md) structures that are associated with a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure. **NET_BUFFER_SHARED_MEM_NEXT_SEGMENT** gets a pointer to the next **NET_BUFFER_SHARED_MEMORY** structure from the **NextSharedMemorySegment** member of the **NET_BUFFER_SHARED_MEMORY** structure. The **SharedMemoryInfo** member of the **NET_BUFFER** structure contains the first **NET_BUFFER_SHARED_MEMORY** structure in the linked list.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

[**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md)