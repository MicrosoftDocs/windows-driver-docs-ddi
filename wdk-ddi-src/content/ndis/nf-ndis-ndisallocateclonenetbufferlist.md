---
UID: NF:ndis.NdisAllocateCloneNetBufferList
title: NdisAllocateCloneNetBufferList function
author: windows-driver-content
description: Call the NdisAllocateCloneNetBufferList function to create a new clone NET_BUFFER_LIST structure.
old-location: netvista\ndisallocateclonenetbufferlist.htm
old-project: netvista
ms.assetid: 357605a1-5c57-44ed-97b3-f466f9a7182c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisAllocateCloneNetBufferList function [Network Drivers Starting with Windows Vista], ndis_netbuf_functions_ref_52fbbc8b-cf3c-4df8-8e02-053946be8136.xml, NdisAllocateCloneNetBufferList, ndis/NdisAllocateCloneNetBufferList, netvista.ndisallocateclonenetbufferlist
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisAllocateCloneNetBufferList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateCloneNetBufferList function


## -description


Call the 
  <b>NdisAllocateCloneNetBufferList</b> function to create a new clone 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -syntax


````
PNET_BUFFER_LIST NdisAllocateCloneNetBufferList(
  _In_     PNET_BUFFER_LIST OriginalNetBufferList,
  _In_opt_ NDIS_HANDLE      NetBufferListPoolHandle,
  _In_opt_ NDIS_HANDLE      NetBufferPoolHandle,
  _In_     ULONG            AllocateCloneFlags
);
````


## -parameters




#### - OriginalNetBufferList [in]

A pointer to an existing <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


#### - NetBufferListPoolHandle [in, optional]

A handle that was obtained from a call to the 
     <mshelp:link keywords="netvista.ndisallocatenetbufferlistpool" tabindex="0"><b>
     NdisAllocateNetBufferListPool</b></mshelp:link> function.


#### - NetBufferPoolHandle [in, optional]

A 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure pool handle that was
     previously returned from a call to 
     <mshelp:link keywords="netvista.ndisallocatenetbufferpool" tabindex="0"><b>
     NdisAllocateNetBufferPool</b></mshelp:link>.


#### - AllocateCloneFlags [in]

NDIS flags that can be combined with an OR operation. The following flags are defined:
     




#### NDIS_CLONE_FLAGS_RESERVED

Reserved for NDIS.


#### NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS

If this flag is set, NDIS does not allocate new MDLs for the cloned <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>. Instead,
       the cloned <b>NET_BUFFER_LIST</b> uses the same MDL chain as the original <b>NET_BUFFER_LIST</b>. If
       NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS is cleared, NDIS allocates new MDLs to reference the original data
       buffers.


## -returns


<b>NdisAllocateCloneNetBufferList</b> returns a pointer to the new clone <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. If
     the allocation was unsuccessful, this pointer is <b>NULL</b>.



## -remarks


Call 
    <b>NdisAllocateCloneNetBufferList</b> to create a clone 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that you can use
    to send duplicate data on a separate data path.

Each <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure in the original <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure is only cloned from the start of the used data space, not the start of the entire data space. To get the offset from the beginning of the data space to the start of the used data space, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568383">NET_BUFFER_DATA_OFFSET</a>  macro.

If the cloned <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure should have attributes that are associated with a given pool,
    the caller must specify the pool handle in the 
    <i>NetBufferListPoolHandle</i> or 
    <i>NetBufferPoolHandle</i> parameter. For example, the 
    <b>ProtocolType</b> member of the <b>NET_BUFFER_LIST</b> structure is associated with the pool.

The clone <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure describes the same data that is described by the <b>NET_BUFFER_LIST</b>
    structure at 
    <i>OriginalNetBufferList</i>. NDIS does not copy the data that is described by the original MDLs to new
    data buffers. Instead, the cloned structures reference the original data buffers. The clone
    <b>NET_BUFFER_LIST</b> structure does not include an initial 
    <mshelp:link keywords="netvista.net_buffer_list_context" tabindex="0"><b>
    NET_BUFFER_LIST_CONTEXT</b></mshelp:link> structure.

Call the 
    <mshelp:link keywords="netvista.ndisfreeclonenetbufferlist" tabindex="0"><b>
    NdisFreeCloneNetBufferList</b></mshelp:link> function to free a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure and all of the associated
    structures and MDL chains that were allocated by calling 
    <b>NdisAllocateCloneNetBufferList</b>.



## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list_context.md">NET_BUFFER_LIST_CONTEXT</a>

<a href="..\ndis\nf-ndis-ndisfreeclonenetbufferlist.md">NdisFreeCloneNetBufferList</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\ndis\nf-ndis-ndisallocatenetbufferpool.md">NdisAllocateNetBufferPool</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<mshelp:link keywords="netvista.ndisallocatenetbufferlistpool" tabindex="0"><b>
   NdisAllocateNetBufferListPool</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateCloneNetBufferList function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

