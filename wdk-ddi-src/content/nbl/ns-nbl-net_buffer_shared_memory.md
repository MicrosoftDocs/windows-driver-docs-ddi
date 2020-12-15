---
UID: NS:nbl._NET_BUFFER_SHARED_MEMORY
title: NET_BUFFER_SHARED_MEMORY
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_SHARED_MEMORY structure specifies a shared memory buffer that is associated with a NET_BUFFER structure.
tech.root: netvista
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndis/nbl.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: NET_BUFFER_SHARED_MEMORY, *PNET_BUFFER_SHARED_MEMORY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nbl.h
api_name:
 - _NET_BUFFER_SHARED_MEMORY
 - PNET_BUFFER_SHARED_MEMORY
 - NET_BUFFER_SHARED_MEMORY
f1_keywords:
 - _NET_BUFFER_SHARED_MEMORY
 - nbl/_NET_BUFFER_SHARED_MEMORY
 - PNET_BUFFER_SHARED_MEMORY
 - nbl/PNET_BUFFER_SHARED_MEMORY
 - NET_BUFFER_SHARED_MEMORY
 - nbl/NET_BUFFER_SHARED_MEMORY
dev_langs:
 - c++
---


# _NET_BUFFER_SHARED_MEMORY structure


## -description

The NET_BUFFER_SHARED_MEMORY structure specifies a shared memory buffer that is associated with a 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -struct-fields

### -field NextSharedMemorySegment

A pointer to the next NET_BUFFER_SHARED_MEMORY structure in a NULL-terminated linked list of such
     structures.

### -field SharedMemoryFlags

A ULONG value that contains shared memory flags. This member is reserved for future use.

### -field SharedMemoryHandle

An NDIS_HANDLE that contains an NDIS shared memory handle.

### -field SharedMemoryOffset

A ULONG value that contains the offset, in bytes, of the shared memory.

### -field SharedMemoryLength

A ULONG value for the length, in bytes, of the shared memory segment.

## -remarks

An NDIS 6.20 or later driver uses the NET_BUFFER_SHARED_MEMORY structure to describe a shared memory
    buffer. There can be a linked list of such shared memory buffers that are associated with a 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. Virtual machine queue (VMQ)
    capable NICs use these shared memory buffers in the virtualization environment.

Use the 
    <a href="/windows-hardware/drivers/network/net-buffer-shared-mem-next-segment">
    NET_BUFFER_SHARED_MEM_NEXT_SEGMENT</a>, 
    <a href="/windows-hardware/drivers/network/net-buffer-shared-mem-flags">NET_BUFFER_SHARED_MEM_FLAGS</a>, 
    <a href="/windows-hardware/drivers/network/net-buffer-shared-mem-handle">NET_BUFFER_SHARED_MEM_HANDLE</a>, 
    <a href="/windows-hardware/drivers/network/net-buffer-shared-mem-offset">NET_BUFFER_SHARED_MEM_OFFSET</a>,
    and 
    <a href="/windows-hardware/drivers/network/net-buffer-shared-mem-length">
    NET_BUFFER_SHARED_MEM_LENGTH</a> macros to access the NET_BUFFER_SHARED_MEMORY in a NET_BUFFER
    structure. The 
    <b>SharedMemoryInfo</b> member of the NET_BUFFER structure contains the first NET_BUFFER_SHARED_MEMORY
    structure in the linked list.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/network/net-buffer-shared-mem-flags">NET_BUFFER_SHARED_MEM_FLAGS</a>



<a href="/windows-hardware/drivers/network/net-buffer-shared-mem-handle">NET_BUFFER_SHARED_MEM_HANDLE</a>



<a href="/windows-hardware/drivers/network/net-buffer-shared-mem-length">NET_BUFFER_SHARED_MEM_LENGTH</a>



<a href="/windows-hardware/drivers/network/net-buffer-shared-mem-next-segment">
   NET_BUFFER_SHARED_MEM_NEXT_SEGMENT</a>



<a href="/windows-hardware/drivers/network/net-buffer-shared-mem-offset">NET_BUFFER_SHARED_MEM_OFFSET</a>

