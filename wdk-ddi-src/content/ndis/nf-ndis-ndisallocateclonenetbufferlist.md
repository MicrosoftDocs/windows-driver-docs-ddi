---
UID: NF:ndis.NdisAllocateCloneNetBufferList
title: NdisAllocateCloneNetBufferList function
description: Call the NdisAllocateCloneNetBufferList function to create a new clone NET_BUFFER_LIST structure.
old-location: netvista\ndisallocateclonenetbufferlist.htm
tech.root: netvista
ms.assetid: 357605a1-5c57-44ed-97b3-f466f9a7182c
ms.date: 05/02/2018
ms.keywords: NdisAllocateCloneNetBufferList, NdisAllocateCloneNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateCloneNetBufferList, ndis_netbuf_functions_ref_52fbbc8b-cf3c-4df8-8e02-053946be8136.xml, netvista.ndisallocateclonenetbufferlist
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisAllocateCloneNetBufferList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateCloneNetBufferList function


## -description


Call the 
  <b>NdisAllocateCloneNetBufferList</b> function to create a new clone 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


## -parameters




### -param OriginalNetBufferList [in]

A pointer to an existing <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


### -param NetBufferListPoolHandle [in, optional]

A handle that was obtained from a call to the 
     <a href="https://msdn.microsoft.com/b117b472-0c26-41a9-b364-3d0cfbd26cc9">
     NdisAllocateNetBufferListPool</a> function.


### -param NetBufferPoolHandle [in, optional]

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure pool handle that was
     previously returned from a call to 
     <a href="https://msdn.microsoft.com/bc27758a-a793-48a1-a6ab-bd193aa9c61a">
     NdisAllocateNetBufferPool</a>.


### -param AllocateCloneFlags [in]

NDIS flags that can be combined with an OR operation. The following flags are defined:
     





#### NDIS_CLONE_FLAGS_RESERVED

Reserved for NDIS.



#### NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS

If this flag is set, NDIS does not allocate new MDLs for the cloned <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>. Instead,
       the cloned <b>NET_BUFFER_LIST</b> uses the same MDL chain as the original <b>NET_BUFFER_LIST</b>. If
       NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS is cleared, NDIS allocates new MDLs to reference the original data
       buffers.


## -returns



<b>NdisAllocateCloneNetBufferList</b> returns a pointer to the new clone <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. If
     the allocation was unsuccessful, this pointer is <b>NULL</b>.




## -remarks



Call 
    <b>NdisAllocateCloneNetBufferList</b> to create a clone 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that you can use
    to send duplicate data on a separate data path.

Each <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure in the original <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure is only cloned from the start of the used data space, not the start of the entire data space. To get the offset from the beginning of the data space to the start of the used data space, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568383">NET_BUFFER_DATA_OFFSET</a>  macro.

If the cloned <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure should have attributes that are associated with a given pool,
    the caller must specify the pool handle in the 
    <i>NetBufferListPoolHandle</i> or 
    <i>NetBufferPoolHandle</i> parameter. For example, the 
    <b>ProtocolType</b> member of the <b>NET_BUFFER_LIST</b> structure is associated with the pool.

The clone <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure describes the same data that is described by the <b>NET_BUFFER_LIST</b>
    structure at 
    <i>OriginalNetBufferList</i>. NDIS does not copy the data that is described by the original MDLs to new
    data buffers. Instead, the cloned structures reference the original data buffers. The clone
    <b>NET_BUFFER_LIST</b> structure does not include an initial 
    <a href="https://msdn.microsoft.com/e5d70be6-daa5-4d2e-94fd-5739edd8821e">
    NET_BUFFER_LIST_CONTEXT</a> structure.

Call the 
    <a href="https://msdn.microsoft.com/3c632d54-8eb2-475b-8cdf-363028f67437">
    NdisFreeCloneNetBufferList</a> function to free a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure and all of the associated
    structures and MDL chains that were allocated by calling 
    <b>NdisAllocateCloneNetBufferList</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568389">NET_BUFFER_LIST_CONTEXT</a>



<a href="https://msdn.microsoft.com/b117b472-0c26-41a9-b364-3d0cfbd26cc9">
   NdisAllocateNetBufferListPool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561613">NdisAllocateNetBufferPool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561841">NdisFreeCloneNetBufferList</a>
 

 

