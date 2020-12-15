---
UID: NF:nblapi.NdisFreeCloneNetBufferList
title: NdisFreeCloneNetBufferList
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisFreeCloneNetBufferList function to free a NET_BUFFER_LIST structure and all associated NET_BUFFER structures and MDL chains that were previously allocated by calling the NdisAllocateCloneNetBufferList function.
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
 - NdisFreeCloneNetBufferList
f1_keywords:
 - NdisFreeCloneNetBufferList
 - nblapi/NdisFreeCloneNetBufferList
dev_langs:
 - c++
---

# NdisFreeCloneNetBufferList function


## -description

Call the 
  <b>NdisFreeCloneNetBufferList</b> function to free a 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure and all associated 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures and MDL chains that were
  previously allocated by calling the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
  NdisAllocateCloneNetBufferList</a> function.

## -parameters

### -param CloneNetBufferList 

[in]
A pointer to a NET_BUFFER_LIST structure that was allocated by calling 
     <b>NdisAllocateCloneNetBufferList</b>.

### -param FreeCloneFlags 

[in]
NDIS flags that can be combined with an OR operation. The following flags are defined:
     





#### NDIS_CLONE_FLAGS_RESERVED

Reserved for NDIS.



#### NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS

If this flag is set, NDIS did not allocate new MDLs for the cloned NET_BUFFER_LIST in the 
       <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
       NdisAllocateCloneNetBufferList</a> function. Instead, the cloned NET_BUFFER_LIST used the same MDL
       chain as in the original NET_BUFFER_LIST. If NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS is cleared, NDIS
       allocated new MDLs to reference the original data buffers.

## -remarks

The caller must specifiy the same flags that it specified in the 
    <i>AllocateCloneFlags</i> parameter when it called the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
    NdisAllocateCloneNetBufferList</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
   NdisAllocateCloneNetBufferList</a>
