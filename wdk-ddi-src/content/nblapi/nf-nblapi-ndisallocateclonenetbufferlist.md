---
UID: NF:nblapi.NdisAllocateCloneNetBufferList
title: NdisAllocateCloneNetBufferList
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisAllocateCloneNetBufferList function to create a new clone NET_BUFFER_LIST structure.
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
 - NdisAllocateCloneNetBufferList
f1_keywords:
 - NdisAllocateCloneNetBufferList
 - nblapi/NdisAllocateCloneNetBufferList
dev_langs:
 - c++
---

# NdisAllocateCloneNetBufferList function


## -description

Call the 
  <b>NdisAllocateCloneNetBufferList</b> function to create a new clone 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

## -parameters

### -param OriginalNetBufferList 

[in]
A pointer to an existing <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

### -param NetBufferListPoolHandle 

[in, optional]
A handle that was obtained from a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
     NdisAllocateNetBufferListPool</a> function.

### -param NetBufferPoolHandle 

[in, optional]
A 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure pool handle that was
     previously returned from a call to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">
     NdisAllocateNetBufferPool</a>.

### -param AllocateCloneFlags 

[in]
NDIS flags that can be combined with an OR operation. The following flags are defined:
     





#### NDIS_CLONE_FLAGS_RESERVED

Reserved for NDIS.



#### NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS

If this flag is set, NDIS does not allocate new MDLs for the cloned <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>. Instead,
       the cloned <b>NET_BUFFER_LIST</b> uses the same MDL chain as the original <b>NET_BUFFER_LIST</b>. If
       NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS is cleared, NDIS allocates new MDLs to reference the original data
       buffers.

## -returns

<b>NdisAllocateCloneNetBufferList</b> returns a pointer to the new clone <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure. If
     the allocation was unsuccessful, this pointer is <b>NULL</b>.

## -remarks

Call 
    <b>NdisAllocateCloneNetBufferList</b> to create a clone 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure that you can use
    to send duplicate data on a separate data path.

Each <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure in the original <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure is only cloned from the start of the used data space, not the start of the entire data space. To get the offset from the beginning of the data space to the start of the used data space, use the <a href="/windows-hardware/drivers/network/net-buffer-data-offset">NET_BUFFER_DATA_OFFSET</a>  macro.

If the cloned <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure should have attributes that are associated with a given pool,
    the caller must specify the pool handle in the 
    <i>NetBufferListPoolHandle</i> or 
    <i>NetBufferPoolHandle</i> parameter. For example, the 
    <b>ProtocolType</b> member of the <b>NET_BUFFER_LIST</b> structure is associated with the pool.

The clone <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure describes the same data that is described by the <b>NET_BUFFER_LIST</b>
    structure at 
    <i>OriginalNetBufferList</i>. NDIS does not copy the data that is described by the original MDLs to new
    data buffers. Instead, the cloned structures reference the original data buffers. The clone
    <b>NET_BUFFER_LIST</b> structure does not include an initial 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">
    NET_BUFFER_LIST_CONTEXT</a> structure.

Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreeclonenetbufferlist">
    NdisFreeCloneNetBufferList</a> function to free a <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure and all of the associated
    structures and MDL chains that were allocated by calling 
    <b>NdisAllocateCloneNetBufferList</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">NdisAllocateNetBufferPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreeclonenetbufferlist">NdisFreeCloneNetBufferList</a>

