---
UID: NF:nblapi.NdisAllocateReassembledNetBufferList
title: NdisAllocateReassembledNetBufferList
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisAllocateReassembledNetBufferList function to reassemble a fragmented NET_BUFFER_LIST structure.
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
 - NdisAllocateReassembledNetBufferList
f1_keywords:
 - NdisAllocateReassembledNetBufferList
 - nblapi/NdisAllocateReassembledNetBufferList
dev_langs:
 - c++
---


# NdisAllocateReassembledNetBufferList function


## -description

Call the 
  <b>NdisAllocateReassembledNetBufferList</b> function to reassemble a fragmented 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

## -parameters

### -param FragmentNetBufferList

A pointer to the NET_BUFFER_LIST structure to reassemble.

### -param NetBufferAndNetBufferListPoolHandle 

[in, optional]
A NET_BUFFER_LIST structure pool handle that was previously returned from the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
     NdisAllocateNetBufferListPool</a> function. The 
     <b>fAllocateNetBuffer</b> member of the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure that the caller passed to 
     <b>NdisAllocateNetBufferListPool</b> must have been set to <b>TRUE</b>, and the 
     <b>DataSize</b> member set to zero. If this parameter is <b>NULL</b>, NDIS uses an internal pool.

### -param StartOffset 

[in]
The amount of data to skip at the beginning of each source 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. This amount is in addition
     to the value that is specified in the 
     <b>DataOffset</b> member of the NET_BUFFER structure.

### -param DataOffsetDelta 

[in]
The number of bytes of 
     <i>used data space</i> to add to in the reassembled NET_BUFFER structure.

### -param DataBackFill 

[in]
If allocation of 
     <i>unused data space</i> (backfill space) is required, this parameter specifies the number of bytes of 
     <i>unused data space</i> in addition to 
     <i>DataOffsetDelta</i> to allocate.

### -param AllocateReassembleFlags 

[in]
NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.

## -returns

If the reassemble operation succeeds, 
     <b>NdisAllocateReassembledNetBufferList</b> returns a reassembled NET_BUFFER_LIST structure. If the
     operation fails, it returns <b>NULL</b>.

## -remarks

<b>NdisAllocateReassembledNetBufferList</b> allocates, initializes, and returns a new 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure that includes one 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure and one MDL chain. The new
    NET_BUFFER_LIST structure describes the same data as the fragmented source NET_BUFFER_LIST structure that
    the driver passed at 
    <i>FragmentedNetBufferList</i>. After skipping the number of bytes specified in 
    <i>StartOffset</i> in every fragmented NET_BUFFER structure, NDIS concatenates the remaining data in each
    fragmented NET_BUFFER structure into one reassembled NET_BUFFER structure. Reassembled NET_BUFFER_LIST
    structures do not include an initial 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">
    NET_BUFFER_LIST_CONTEXT</a> structure.

Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreereassemblednetbufferlist">
    NdisFreeReassembledNetBufferList</a> function to free a reassembled NET_BUFFER_LIST structure and all
    of the associated NET_BUFFER structures and MDL chains.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreereassemblednetbufferlist">
   NdisFreeReassembledNetBufferList</a>

