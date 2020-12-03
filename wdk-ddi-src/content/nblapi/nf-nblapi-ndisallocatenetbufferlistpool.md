---
UID: NF:nblapi.NdisAllocateNetBufferListPool
title: NdisAllocateNetBufferListPool
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisAllocateNetBufferListPool function to allocate a pool of NET_BUFFER_LIST structures.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function
req.dll: Ndis.sys
req.header: ndis/nblapi.h
req.idl: 
req.include-header: ndis.h
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: Ndis.lib
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
 - DllExport
api_location:
 - nblapi.h
api_name:
 - NdisAllocateNetBufferListPool
f1_keywords:
 - NdisAllocateNetBufferListPool
 - nblapi/NdisAllocateNetBufferListPool
dev_langs:
 - c++
---

# NdisAllocateNetBufferListPool function


## -description

Call the 
  <b>NdisAllocateNetBufferListPool</b> function to allocate a pool of 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures.

## -parameters

### -param NdisHandle 

[in, optional]
An NDIS handle that was obtained during caller initialization.

### -param Parameters 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure that defines the parameters for the pool.

## -returns

<b>NdisAllocateNetBufferListPool</b> returns a handle to the NET_BUFFER_LIST structure pool that NDIS
     allocates. If the allocation was unsuccessful, this handle is <b>NULL</b>. This handle is a required parameter
     in subsequent calls to NDIS functions that allocate and free NET_BUFFER_LIST structures from this
     pool.

## -remarks

In most cases, a caller that allocates a 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure will allocate and
    queue at least one 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure on that NET_BUFFER_LIST
    structure. It is more efficient to preallocate NET_BUFFER structures when you allocate a pool of
    NET_BUFFER_LIST structures than allocating NET_BUFFER_LIST structures and NET_BUFFER structures
    separately.

You can call the 
    <b>NdisAllocateNetBufferListPool</b> function with the 
    <b>fAllocateNetBuffer</b> value set to <b>TRUE</b> when creating a NET_BUFFER_LIST structure pool. In this case,
    a NET_BUFFER structure is preallocated with each NET_BUFFER_LIST structure that the caller allocates from
    the pool. You can call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
    NdisAllocateNetBufferAndNetBufferList</a> function or the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">
    NdisAllocateNetBufferList</a> function to allocate NET_BUFFER_LIST structures from such a pool. Call 
    <b>NdisAllocateNetBufferAndNetBufferList</b> only if 
    <b>fAllocateNetBuffer</b> is <b>TRUE</b> and 
    <b>DataSize</b> is zero.

You can also call 
    <b>NdisAllocateNetBufferListPool</b> and set the 
    <b>DataSize</b> member to a nonzero value when creating a NET_BUFFER_LIST structure pool. In this case, a
    NET_BUFFER structure, MDL, and data are preallocated with each NET_BUFFER_LIST structure that the caller
    allocates from the pool.

NET_BUFFER structures, MDLs, and data buffers that are allocated with 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
    NdisAllocateNetBufferAndNetBufferList</a> or 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a> should
    not be freed separate from the NET_BUFFER_LIST structure. Such structures are freed with the
    NET_BUFFER_LIST structure when you call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a> function.

Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlistpool">
    NdisFreeNetBufferListPool</a> function to free a NET_BUFFER_LIST structure pool.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlistpool">NdisFreeNetBufferListPool</a>
