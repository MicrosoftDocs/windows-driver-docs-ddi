---
UID: NF:nblapi.NdisAllocateNetBufferListContext
title: NdisAllocateNetBufferListContext
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisAllocateNetBufferListContext function to allocate more context space in the NET_BUFFER_LIST_CONTEXT structure of a NET_BUFFER_LIST structure.
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
 - NdisAllocateNetBufferListContext
f1_keywords:
 - NdisAllocateNetBufferListContext
 - nblapi/NdisAllocateNetBufferListContext
dev_langs:
 - c++
---

# NdisAllocateNetBufferListContext function


## -description

Call the 
  <b>NdisAllocateNetBufferListContext</b> function to allocate more context space in the 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure of a
  
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

## -parameters

### -param NetBufferList 

[in]
A pointer to a previously allocated NET_BUFFER_LIST structure.

### -param ContextSize 

[in]
The amount of context space to allocate in the NET_BUFFER_LIST_CONTEXT structure. This amount must
     be a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.

### -param ContextBackFill 

[in]
The amount of memory, in addition to the value of 
     <i>ContextSize</i>, to allocate if NDIS must allocate memory to satisfy the request. This amount must be
     a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.

### -param PoolTag 

[in]
A kernel pool tag that NDIS uses to allocate the memory for the NET_BUFFER_LIST_CONTEXT structure,
     if allocation is required. The tag is a string, delimited by single quotation marks, with up to four
     characters, usually specified in reversed order. The kernel pool tag helps NDIS to identify the owner of
     the memory.

## -returns

<b>NdisAllocateNetBufferListContext</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisAllocateNetBufferListContext</b> successfully allocated context space either by reducing the
       value of the 
       <b>Offset</b> member of the NET_BUFFER_LIST_CONTEXT structure or by allocating new memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisAllocateNetBufferListContext</b> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisAllocateNetBufferListContext</b> failed for reasons other than insufficient resources.

</td>
</tr>
</table>

## -remarks

If there is enough unused context space available in the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure to
    satisfy the request, 
    <b>NdisAllocateNetBufferListContext</b> simply reduces the value of the 
    <b>Offset</b> member in the NET_BUFFER_LIST_CONTEXT structure. Otherwise, NDIS allocates new memory for
    context space. You can specify 
    <i>ContextBackFill</i> to allocate extra memory so that the next call to 
    <b>NdisAllocateNetBufferListContext</b> does not have to allocate memory.

Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlistcontext">
    NdisFreeNetBufferListContext</a> function to release the context space in the NET_BUFFER_LIST_CONTEXT
    structure that was allocated with 
    <b>NdisAllocateNetBufferListContext</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlistcontext">NdisFreeNetBufferListContext</a>