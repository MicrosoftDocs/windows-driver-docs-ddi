---
UID: NF:ndis.NdisAllocateNetBufferListContext
title: NdisAllocateNetBufferListContext function (ndis.h)
description: Call the NdisAllocateNetBufferListContext function to allocate more context space in the NET_BUFFER_LIST_CONTEXT structure of a NET_BUFFER_LIST structure.
old-location: netvista\ndisallocatenetbufferlistcontext.htm
tech.root: netvista
ms.assetid: 3bbad723-86bf-4206-9e51-52a66efaec20
ms.date: 05/02/2018
keywords: ["NdisAllocateNetBufferListContext function"]
ms.keywords: NdisAllocateNetBufferListContext, NdisAllocateNetBufferListContext function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateNetBufferListContext, ndis_netbuf_functions_ref_f421f804-e12d-43ba-81ed-d5322712faf5.xml, netvista.ndisallocatenetbufferlistcontext
f1_keywords:
 - "ndis/NdisAllocateNetBufferListContext"
 - "NdisAllocateNetBufferListContext"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisAllocateNetBufferListContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateNetBufferListContext function


## -description


Call the 
  <b>NdisAllocateNetBufferListContext</b> function to allocate more context space in the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure of a
  
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.


## -parameters




### -param NetBufferList [in]

A pointer to a previously allocated NET_BUFFER_LIST structure.


### -param ContextSize [in]

The amount of context space to allocate in the NET_BUFFER_LIST_CONTEXT structure. This amount must
     be a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.


### -param ContextBackFill [in]

The amount of memory, in addition to the value of 
     <i>ContextSize</i>, to allocate if NDIS must allocate memory to satisfy the request. This amount must be
     a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.


### -param PoolTag [in]

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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure to
    satisfy the request, 
    <b>NdisAllocateNetBufferListContext</b> simply reduces the value of the 
    <b>Offset</b> member in the NET_BUFFER_LIST_CONTEXT structure. Otherwise, NDIS allocates new memory for
    context space. You can specify 
    <i>ContextBackFill</i> to allocate extra memory so that the next call to 
    <b>NdisAllocateNetBufferListContext</b> does not have to allocate memory.

Call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlistcontext">
    NdisFreeNetBufferListContext</a> function to release the context space in the NET_BUFFER_LIST_CONTEXT
    structure that was allocated with 
    <b>NdisAllocateNetBufferListContext</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlistcontext">NdisFreeNetBufferListContext</a>
 

 

