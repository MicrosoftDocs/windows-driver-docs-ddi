---
UID: NF:nblaccessors.NET_BUFFER_SHARED_MEM_FLAGS
title: NET_BUFFER_SHARED_MEM_FLAGS
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_SHARED_MEM_FLAGS macro gets the shared memory flags from a NET_BUFFER_SHARED_MEMORY structure.
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
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
 - NET_BUFFER_SHARED_MEM_FLAGS
f1_keywords:
 - NET_BUFFER_SHARED_MEM_FLAGS
 - nblaccessors/NET_BUFFER_SHARED_MEM_FLAGS
dev_langs:
 - c++
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