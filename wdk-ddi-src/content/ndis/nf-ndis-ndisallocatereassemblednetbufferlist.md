---
UID: NF:ndis.NdisAllocateReassembledNetBufferList
title: NdisAllocateReassembledNetBufferList function
author: windows-driver-content
description: Call the NdisAllocateReassembledNetBufferList function to reassemble a fragmented NET_BUFFER_LIST structure.
old-location: netvista\ndisallocatereassemblednetbufferlist.htm
old-project: netvista
ms.assetid: 6a7fcb43-93bf-4351-8198-1d788b1bcc8c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis_netbuf_functions_ref_20c58532-de90-4594-9bd8-5393a70c6b80.xml, NdisAllocateReassembledNetBufferList, netvista.ndisallocatereassemblednetbufferlist, ndis/NdisAllocateReassembledNetBufferList, NdisAllocateReassembledNetBufferList function [Network Drivers Starting with Windows Vista]
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
-	NdisAllocateReassembledNetBufferList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateReassembledNetBufferList function


## -description


Call the 
  <b>NdisAllocateReassembledNetBufferList</b> function to reassemble a fragmented 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -syntax


````
PNET_BUFFER_LIST NdisAllocateReassembledNetBufferList(
  _In_     PNET_BUFFER_LIST FragmentedNetBufferList,
  _In_opt_ NDIS_HANDLE      NetBufferAndNetBufferListPoolHandle,
  _In_     ULONG            StartOffset,
  _In_     ULONG            DataOffsetDelta,
  _In_     ULONG            DataBackFill,
  _In_     ULONG            AllocateReassembleFlags
);
````


## -parameters




### -param FragmentNetBufferList

TBD


### -param NetBufferAndNetBufferListPoolHandle [in, optional]

A NET_BUFFER_LIST structure pool handle that was previously returned from the 
     <mshelp:link keywords="netvista.ndisallocatenetbufferlistpool" tabindex="0"><b>
     NdisAllocateNetBufferListPool</b></mshelp:link> function. The 
     <b>fAllocateNetBuffer</b> member of the 
     <a href="..\ndis\ns-ndis-_net_buffer_list_pool_parameters.md">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure that the caller passed to 
     <b>NdisAllocateNetBufferListPool</b> must have been set to <b>TRUE</b>, and the 
     <b>DataSize</b> member set to zero. If this parameter is <b>NULL</b>, NDIS uses an internal pool.


### -param StartOffset [in]

The amount of data to skip at the beginning of each source 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure. This amount is in addition
     to the value that is specified in the 
     <b>DataOffset</b> member of the NET_BUFFER structure.


### -param DataOffsetDelta [in]

The number of bytes of 
     <i>used data space</i> to add to in the reassembled NET_BUFFER structure.


### -param DataBackFill [in]

If allocation of 
     <i>unused data space</i> (backfill space) is required, this parameter specifies the number of bytes of 
     <i>unused data space</i> in addition to 
     <i>DataOffsetDelta</i> to allocate.


### -param AllocateReassembleFlags [in]

NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.


#### - FragmentedNetBufferList [in]

A pointer to the NET_BUFFER_LIST structure to reassemble.


## -returns


If the reassemble operation succeeds, 
     <b>NdisAllocateReassembledNetBufferList</b> returns a reassembled NET_BUFFER_LIST structure. If the
     operation fails, it returns <b>NULL</b>.



## -remarks


<b>NdisAllocateReassembledNetBufferList</b> allocates, initializes, and returns a new 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that includes one 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure and one MDL chain. The new
    NET_BUFFER_LIST structure describes the same data as the fragmented source NET_BUFFER_LIST structure that
    the driver passed at 
    <i>FragmentedNetBufferList</i>. After skipping the number of bytes specified in 
    <i>StartOffset</i> in every fragmented NET_BUFFER structure, NDIS concatenates the remaining data in each
    fragmented NET_BUFFER structure into one reassembled NET_BUFFER structure. Reassembled NET_BUFFER_LIST
    structures do not include an initial 
    <mshelp:link keywords="netvista.net_buffer_list_context" tabindex="0"><b>
    NET_BUFFER_LIST_CONTEXT</b></mshelp:link> structure.

Call the 
    <mshelp:link keywords="netvista.ndisfreereassemblednetbufferlist" tabindex="0"><b>
    NdisFreeReassembledNetBufferList</b></mshelp:link> function to free a reassembled NET_BUFFER_LIST structure and all
    of the associated NET_BUFFER structures and MDL chains.



## -see-also

<mshelp:link keywords="netvista.ndisallocatenetbufferlistpool" tabindex="0"><b>
   NdisAllocateNetBufferListPool</b></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer_list_pool_parameters.md">NET_BUFFER_LIST_POOL_PARAMETERS</a>

<mshelp:link keywords="netvista.ndisfreereassemblednetbufferlist" tabindex="0"><b>
   NdisFreeReassembledNetBufferList</b></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer_list_context.md">NET_BUFFER_LIST_CONTEXT</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateReassembledNetBufferList function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

