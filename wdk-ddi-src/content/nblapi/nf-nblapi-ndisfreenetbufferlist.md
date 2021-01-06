---
UID: NF:nblapi.NdisFreeNetBufferList
title: NdisFreeNetBufferList
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisFreeNetBufferList function to free a NET_BUFFER_LIST structure that was previously allocated from a NET_BUFFER_LIST structure pool.
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
 - NdisFreeNetBufferList
f1_keywords:
 - NdisFreeNetBufferList
 - nblapi/NdisFreeNetBufferList
dev_langs:
 - c++
---

# NdisFreeNetBufferList function


## -description

Call the 
  <b>NdisFreeNetBufferList</b> function to free a 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure that was previously
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
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure from a pool, call
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



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistcontext">
   NdisAllocateNetBufferListContext</a>
