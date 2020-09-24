---
UID: NF:ndis.NdisAllocateNetBufferList
title: NdisAllocateNetBufferList function (ndis.h)
description: Call the NdisAllocateNetBufferList function to allocate and initialize a NET_BUFFER_LIST structure from a NET_BUFFER_LIST structure pool.
old-location: netvista\ndisallocatenetbufferlist.htm
tech.root: netvista
ms.assetid: 9c821aac-9abd-4041-a15e-64306ada1c02
ms.date: 05/02/2018
keywords: ["NdisAllocateNetBufferList function"]
ms.keywords: NdisAllocateNetBufferList, NdisAllocateNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateNetBufferList, ndis_netbuf_functions_ref_85e4ad07-739d-4c37-b436-d9ca95c9db92.xml, netvista.ndisallocatenetbufferlist
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
 - NdisAllocateNetBufferList
 - ndis/NdisAllocateNetBufferList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisAllocateNetBufferList
---

# NdisAllocateNetBufferList function


## -description

Call the 
  <b>NdisAllocateNetBufferList</b> function to allocate and initialize a 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure from a
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
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure from a pool.

<div class="alert"><b>Note</b>  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures must be allocated
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



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a>