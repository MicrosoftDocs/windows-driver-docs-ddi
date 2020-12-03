---
UID: NF:nblapi.NdisAllocateNetBufferList
title: NdisAllocateNetBufferList
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisAllocateNetBufferList function to allocate and initialize a NET_BUFFER_LIST structure from a NET_BUFFER_LIST structure pool.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function
req.dll: 
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
 - LibDef
api_location:
 - nblapi.h
api_name:
 - NdisAllocateNetBufferList
f1_keywords:
 - NdisAllocateNetBufferList
 - nblapi/NdisAllocateNetBufferList
dev_langs:
 - c++
---

# NdisAllocateNetBufferList function


## -description

Call the 
  <b>NdisAllocateNetBufferList</b> function to allocate and initialize a 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure from a
  NET_BUFFER_LIST structure pool.

## -parameters

### -param PoolHandle 

[in]
A NET_BUFFER_LIST structure pool handle that was previously returned from a call to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
     NdisAllocateNetBufferListPool</a>.

### -param ContextSize 

[in]
The amount of 
     <i>used data space</i> in the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure
     to reserve for the caller. The 
     <i>ContextSize</i> must be a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.

### -param ContextBackFill 

[in]
The amount of 
     <i>unused data space</i> (backfill space) that the caller requires. NDIS adds this value to the 
     <i>ContextSize</i> and allocates additional space. The 
     <i>ContextBackFill</i> must be a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.

## -returns

<b>NdisAllocateNetBufferList</b> returns a pointer to the allocated NET_BUFFER_LIST structure. If the
     allocation was unsuccessful, this pointer is <b>NULL</b>.

## -remarks

You can call the 
    <b>NdisAllocateNetBufferList</b> or 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
    NdisAllocateNetBufferAndNetBufferList</a> function to allocate a 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure from a pool.

<div class="alert"><b>Note</b>  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> and 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures must be allocated
    from an NDIS buffer pool. A driver must not allocate and initialize a NET_BUFFER_LIST or NET_BUFFER
    structure from its private memory pool or the stack.</div>
<div> </div>
If you call 
    <b>NdisAllocateNetBufferList</b> and the NET_BUFFER_LIST structure pool was allocated by calling the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
    NdisAllocateNetBufferListPool</a> function with the 
    <b>fAllocateNetBuffer</b> member of the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure set to <b>TRUE</b>, NDIS allocates a
    NET_BUFFER_LIST, 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>, MDL, and data.

Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a> function to
    free a NET_BUFFER_LIST structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a>