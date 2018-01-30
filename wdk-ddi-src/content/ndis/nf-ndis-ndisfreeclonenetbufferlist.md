---
UID: NF:ndis.NdisFreeCloneNetBufferList
title: NdisFreeCloneNetBufferList function
author: windows-driver-content
description: Call the NdisFreeCloneNetBufferList function to free a NET_BUFFER_LIST structure and all associated NET_BUFFER structures and MDL chains that were previously allocated by calling the NdisAllocateCloneNetBufferList function.
old-location: netvista\ndisfreeclonenetbufferlist.htm
old-project: netvista
ms.assetid: 3c632d54-8eb2-475b-8cdf-363028f67437
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisfreeclonenetbufferlist, NdisFreeCloneNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeCloneNetBufferList, NdisFreeCloneNetBufferList, ndis_netbuf_functions_ref_a8be507f-e574-4cbe-ab9e-b48cbe00a5f6.xml
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
-	NdisFreeCloneNetBufferList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeCloneNetBufferList function


## -description


Call the 
  <b>NdisFreeCloneNetBufferList</b> function to free a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure and all associated 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures and MDL chains that were
  previously allocated by calling the 
  <mshelp:link keywords="netvista.ndisallocateclonenetbufferlist" tabindex="0"><b>
  NdisAllocateCloneNetBufferList</b></mshelp:link> function.


## -syntax


````
VOID NdisFreeCloneNetBufferList(
  _In_ PNET_BUFFER_LIST CloneNetBufferList,
  _In_ ULONG            FreeCloneFlags
);
````


## -parameters




### -param CloneNetBufferList [in]

A pointer to a NET_BUFFER_LIST structure that was allocated by calling 
     <b>NdisAllocateCloneNetBufferList</b>.


### -param FreeCloneFlags [in]

NDIS flags that can be combined with an OR operation. The following flags are defined:
     




#### NDIS_CLONE_FLAGS_RESERVED

Reserved for NDIS.


#### NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS

If this flag is set, NDIS did not allocate new MDLs for the cloned NET_BUFFER_LIST in the 
       <mshelp:link keywords="netvista.ndisallocateclonenetbufferlist" tabindex="0"><b>
       NdisAllocateCloneNetBufferList</b></mshelp:link> function. Instead, the cloned NET_BUFFER_LIST used the same MDL
       chain as in the original NET_BUFFER_LIST. If NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS is cleared, NDIS
       allocated new MDLs to reference the original data buffers.


## -returns


None



## -remarks


The caller must specifiy the same flags that it specified in the 
    <i>AllocateCloneFlags</i> parameter when it called the 
    <mshelp:link keywords="netvista.ndisallocateclonenetbufferlist" tabindex="0"><b>
    NdisAllocateCloneNetBufferList</b></mshelp:link> function.



## -see-also

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<mshelp:link keywords="netvista.ndisallocateclonenetbufferlist" tabindex="0"><b>
   NdisAllocateCloneNetBufferList</b></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeCloneNetBufferList function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

