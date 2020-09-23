---
UID: NF:ndis.NdisAllocateNetBufferAndNetBufferList
title: NdisAllocateNetBufferAndNetBufferList function (ndis.h)
description: Call the NdisAllocateNetBufferAndNetBufferList function to allocate and initialize a NET_BUFFER_LIST structure that is initialized with a preallocated NET_BUFFER structure.
old-location: netvista\ndisallocatenetbufferandnetbufferlist.htm
tech.root: netvista
ms.assetid: b872eff3-2d0a-4f01-874d-e00e09195801
ms.date: 05/02/2018
keywords: ["NdisAllocateNetBufferAndNetBufferList function"]
ms.keywords: NdisAllocateNetBufferAndNetBufferList, NdisAllocateNetBufferAndNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateNetBufferAndNetBufferList, ndis_netbuf_functions_ref_47bf06b7-b76e-42a0-bf16-b3942fde8eb9.xml, netvista.ndisallocatenetbufferandnetbufferlist
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisAllocateNetBufferAndNetBufferList
 - ndis/NdisAllocateNetBufferAndNetBufferList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisAllocateNetBufferAndNetBufferList
---

# NdisAllocateNetBufferAndNetBufferList function


## -description

Call the 
  <b>NdisAllocateNetBufferAndNetBufferList</b> function to allocate and initialize a 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that is initialized
  with a preallocated 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -parameters

### -param PoolHandle 

[in]
A NET_BUFFER_LIST structure pool handle that was previously returned from the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
     NdisAllocateNetBufferListPool</a> function. The 
     <b>fAllocateNetBuffer</b> member of the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure that the caller passed to 
     <b>NdisAllocateNetBufferListPool</b> must have been set to <b>TRUE</b> and the 
     <b>DataSize</b> member set to zero.

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

### -param MdlChain 

[in, optional]
A pointer to an MDL chain that NDIS uses to initialize the preallocated NET_BUFFER structure. 
     <i>MdlChain</i> can be <b>NULL</b>.

### -param DataOffset 

[in]
The initial offset, in bytes, from the start of the buffer to the start of the 
     <i>used data space</i> in the MDL chain. Data space ahead of this offset is 
     <i>unused data space</i>. Therefore, this value also represents the initial amount of available backfill
     space in the MDL chain. If 
     <i>MdlChain</i> is <b>NULL</b>, 
     <i>DataOffset</i> must be 0.

### -param DataLength 

[in]
The length, in bytes, of the 
     <i>used data space</i> in the MDL chain. If 
     <i>MdlChain</i> is <b>NULL</b>, 
     <i>DataLength</i> must be 0.

## -returns

<b>NdisAllocateNetBufferAndNetBufferList</b> returns a pointer to the allocated NET_BUFFER_LIST
     structure. The NET_BUFFER_LIST structure includes a NET_BUFFER structure. If the allocation was
     unsuccessful, this pointer is <b>NULL</b>.

## -remarks

The structures that the 
    <b>NdisAllocateNetBufferAndNetBufferList</b> function allocates must come from a pool that includes 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that are paired
    with preallocated 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures. To create such a pool, you
    must call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
    NdisAllocateNetBufferListPool</a> function with the 
    <b>fAllocateNetBuffer</b> member of the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure set to <b>TRUE</b>, and the 
    <b>DataSize</b> member set to zero.

<div class="alert"><b>Note</b>  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures must be allocated
    from an NDIS buffer pool. A driver must not allocate and initialize a <b>NET_BUFFER_LIST</b> or <b>NET_BUFFER</b>
    structure from its private memory pool or the stack.</div>
<div> </div>
Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a> function to
    free a <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

The preallocated <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> can be reused by reinitializing it with another MDL chain when it owns
    <b>NET_BUFFER</b>, but the 
    <i>DataOffset</i>, 
    <i>DataLength</i>, 
    <i>CurrentMdl</i>, and 
    <i>CurrentMdlOffset</i> fields in the <b>NET_BUFFER</b> must be consistent with the new MDL chain.

For example, if the original MDL chain contains <i>X</i>
<i>DataLength</i> and <i>Y</i>
<i>DataOffset</i>, and 
    <i>CurrentMdl</i> starts with the second MDL (<i>M</i>) in the original MDL chain, 
    <i>CurrentMdlOffset</i> is <i>Z</i>. The 
    <i>MdlChain</i> field in <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_data">NET_BUFFER_DATA</a> then needs to point to a new MDL chain that contains <i>X'</i>
<i>DataLength</i> and <i>Y'</i>
<i>DataOffset</i>. If 
    <i>CurrentMdl</i> starts with the third MDL (<i>M'</i>) in the new MDL chain, 
    <i>CurrentMdlOffset</i> is <i>Z'</i>, and the following macros need to be used to set fields in <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>:


```
NET_BUFFER_FIRST_MDL(_NB) = New MDL chain;
NET_BUFFER_DATA_LENGTH(_NB) = X';
NET_BUFFER_DATA_OFFSET(_NB) = Y';
NET_BUFFER_CURRENT_MDL(_NB) = M';
NET_BUFFER_CURRENT_MDL_OFFSET(_NB) = Z';
```


## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a>