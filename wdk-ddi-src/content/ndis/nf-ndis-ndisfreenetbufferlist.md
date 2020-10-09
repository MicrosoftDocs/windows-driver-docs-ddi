---
UID: NF:ndis.NdisFreeNetBufferList
title: NdisFreeNetBufferList function (ndis.h)
description: Call the NdisFreeNetBufferList function to free a NET_BUFFER_LIST structure that was previously allocated from a NET_BUFFER_LIST structure pool.
old-location: netvista\ndisfreenetbufferlist.htm
tech.root: netvista
ms.assetid: fddfe5f8-900a-4f4c-8c78-a106a4a54d88
ms.date: 05/02/2018
keywords: ["NdisFreeNetBufferList function"]
ms.keywords: NdisFreeNetBufferList, NdisFreeNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBufferList, ndis_netbuf_functions_ref_202dda58-f8c4-442b-9c18-9c9b2b7708af.xml, netvista.ndisfreenetbufferlist
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
 - NdisFreeNetBufferList
 - ndis/NdisFreeNetBufferList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeNetBufferList
---

# NdisFreeNetBufferList function


## -description

Call the 
  <b>NdisFreeNetBufferList</b> function to free a 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that was previously
  allocated from a NET_BUFFER_LIST structure pool.

## -parameters

### -param NetBufferList 

[in]
A pointer to a NET_BUFFER_LIST structure that was allocated by calling the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a> or 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
     NdisAllocateNetBufferAndNetBufferList</a> function.

## -remarks

To allocate a 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure from a pool, call
    the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a> or 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
    NdisAllocateNetBufferAndNetBufferList</a> function.

The 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures that are associated with
    the NET_BUFFER_LIST structure are not freed unless they were preallocated with the NET_BUFFER_LIST
    structure. You can reuse any NET_BUFFER structures that were not preallocated or you should free such
    structures separately.

If you allocated context space for a NET_BUFFER_LIST structure with the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistcontext">
    NdisAllocateNetBufferListContext</a> function, you must free such context space before you free the
    NET_BUFFER_LIST structure. You must not attempt to free the context space that you allocated with 
    <b>NdisAllocateNetBufferList</b> or 
    <b>NdisAllocateNetBufferAndNetBufferList</b> by specifying the 
    <i>ContextSize</i> and 
    <i>ContextBackFill</i> parameters.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistcontext">
   NdisAllocateNetBufferListContext</a>