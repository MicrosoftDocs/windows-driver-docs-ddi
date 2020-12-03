---
UID: NF:nblapi.NdisFreeFragmentNetBufferList
title: NdisFreeFragmentNetBufferList
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisFreeFragmentNetBufferList function to free a NET_BUFFER_LIST structure and all associated NET_BUFFER structures and MDL chains that were previously allocated by the calling NdisAllocateFragmentNetBufferList function.
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
 - NdisFreeFragmentNetBufferList
f1_keywords:
 - NdisFreeFragmentNetBufferList
 - nblapi/NdisFreeFragmentNetBufferList
dev_langs:
 - c++
---

# NdisFreeFragmentNetBufferList function


## -description

Call the 
  <b>NdisFreeFragmentNetBufferList</b> function to free a 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure and all associated 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures and MDL chains that were
  previously allocated by the calling 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefragmentnetbufferlist">
  NdisAllocateFragmentNetBufferList</a> function.

## -parameters

### -param FragmentNetBufferList 

[in]
A pointer to a NET_BUFFER_LIST structure that was allocated by calling 
     <b>NdisAllocateFragmentNetBufferList</b>.

### -param DataOffsetDelta 

[in]
The amount, in bytes, to advance (add to the data offset) the fragment NET_BUFFER structures
     before freeing them. This value should match the value of the 
     <i>DataOffsetDelta</i> parameter that was passed to 
     <b>NdisAllocateFragmentNetBufferList</b> when the NET_BUFFER_LIST structure was created.

### -param FreeFragmentFlags 

[in]
NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefragmentnetbufferlist">
   NdisAllocateFragmentNetBufferList</a>
