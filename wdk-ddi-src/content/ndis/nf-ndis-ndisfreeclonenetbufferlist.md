---
UID: NF:ndis.NdisFreeCloneNetBufferList
title: NdisFreeCloneNetBufferList function (ndis.h)
description: Call the NdisFreeCloneNetBufferList function to free a NET_BUFFER_LIST structure and all associated NET_BUFFER structures and MDL chains that were previously allocated by calling the NdisAllocateCloneNetBufferList function.
old-location: netvista\ndisfreeclonenetbufferlist.htm
tech.root: netvista
ms.assetid: 3c632d54-8eb2-475b-8cdf-363028f67437
ms.date: 05/02/2018
keywords: ["NdisFreeCloneNetBufferList function"]
ms.keywords: NdisFreeCloneNetBufferList, NdisFreeCloneNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeCloneNetBufferList, ndis_netbuf_functions_ref_a8be507f-e574-4cbe-ab9e-b48cbe00a5f6.xml, netvista.ndisfreeclonenetbufferlist
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
 - NdisFreeCloneNetBufferList
 - ndis/NdisFreeCloneNetBufferList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeCloneNetBufferList
---

# NdisFreeCloneNetBufferList function


## -description

Call the 
  <b>NdisFreeCloneNetBufferList</b> function to free a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure and all associated 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures and MDL chains that were
  previously allocated by calling the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
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
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
       NdisAllocateCloneNetBufferList</a> function. Instead, the cloned NET_BUFFER_LIST used the same MDL
       chain as in the original NET_BUFFER_LIST. If NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS is cleared, NDIS
       allocated new MDLs to reference the original data buffers.

## -remarks

The caller must specifiy the same flags that it specified in the 
    <i>AllocateCloneFlags</i> parameter when it called the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
    NdisAllocateCloneNetBufferList</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
   NdisAllocateCloneNetBufferList</a>

