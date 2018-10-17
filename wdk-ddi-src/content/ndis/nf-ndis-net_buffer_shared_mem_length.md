---
UID: NF:ndis.NET_BUFFER_SHARED_MEM_LENGTH
title: NET_BUFFER_SHARED_MEM_LENGTH macro
author: windows-driver-content
description: The NET_BUFFER_SHARED_MEM_LENGTH macro gets the shared memory length from a NET_BUFFER_SHARED_MEMORY structure.
tech.root: netvista
ms.assetid: e6b22dc4-658d-4609-9020-1b0349de13fe
ms.date: 04/13/2018
ms.topic: macro
ms.keywords: NET_BUFFER_SHARED_MEM_LENGTH
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
-	NET_BUFFER_SHARED_MEM_LENGTH
product:
-	Windows
targetos: Windows

---

# NET_BUFFER_SHARED_MEM_LENGTH macro


## -description

The **NET_BUFFER_SHARED_MEM_LENGTH** macro gets the shared memory length from a [**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md) structure.

## -parameters

### -param _SHI

A pointer to a **NET_BUFFER_SHARED_MEMORY** structure.

## -returns

**NET_BUFFER_SHARED_MEM_LENGTH** returns a ULONG value for the length, in bytes, of the shared memory.

## -remarks

An NDIS 6.20 or later driver can use the **NET_BUFFER_SHARED_MEM_LENGTH** macro to get the shared memory length that is associated with a [**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md) structure. **NET_BUFFER_SHARED_MEM_LENGTH** gets the length from the **SharedMemoryLength** member of the **NET_BUFFER_SHARED_MEMORY** structure. The **SharedMemoryInfo** member of the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure contains the first **NET_BUFFER_SHARED_MEMORY** structure in a linked list.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

[**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md)
