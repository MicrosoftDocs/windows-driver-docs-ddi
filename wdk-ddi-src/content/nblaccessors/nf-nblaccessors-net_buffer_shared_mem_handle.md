---
UID: NF:nblaccessors.NET_BUFFER_SHARED_MEM_HANDLE
title: NET_BUFFER_SHARED_MEM_HANDLE
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_SHARED_MEM_HANDLE macro gets the shared memory handle from a NET_BUFFER_SHARED_MEMORY structure.
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
 - NET_BUFFER_SHARED_MEM_HANDLE
f1_keywords:
 - NET_BUFFER_SHARED_MEM_HANDLE
 - nblaccessors/NET_BUFFER_SHARED_MEM_HANDLE
dev_langs:
 - c++
---

# NET_BUFFER_SHARED_MEM_HANDLE macro


## -description

The **NET_BUFFER_SHARED_MEM_HANDLE** macro gets the shared memory handle from a [**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md) structure.

## -parameters

### -param _SHI

A pointer to a **NET_BUFFER_SHARED_MEMORY** structure.

## -returns

**NET_BUFFER_SHARED_MEM_HANDLE** returns an NDIS shared memory handle.

## -remarks

An NDIS 6.20 or later driver can use the **NET_BUFFER_SHARED_MEM_HANDLE** macro to get the shared memory handle that is associated with a [**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md) structure. **NET_BUFFER_SHARED_MEM_HANDLE** gets the handle from the **SharedMemoryHandle** member of the **NET_BUFFER_SHARED_MEMORY** structure. The **SharedMemoryInfo** member of the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure contains the first **NET_BUFFER_SHARED_MEMORY** structure in a linked list.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

[**NET_BUFFER_SHARED_MEMORY**](ns-ndis-_net_buffer_shared_memory.md)

