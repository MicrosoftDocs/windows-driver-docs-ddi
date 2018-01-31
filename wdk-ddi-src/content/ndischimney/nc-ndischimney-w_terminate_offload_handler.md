---
UID: NC:ndischimney.W_TERMINATE_OFFLOAD_HANDLER
title: W_TERMINATE_OFFLOAD_HANDLER
author: windows-driver-content
description: The MiniportTerminateOffload function terminates the offload of one or more state objects.
old-location: netvista\miniportterminateoffload.htm
old-project: netvista
ms.assetid: 1b808e3c-2d64-44c9-88d3-0a0311e1dc99
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportterminateoffload, MiniportTerminateOffload callback function [Network Drivers Starting with Windows Vista], MiniportTerminateOffload, W_TERMINATE_OFFLOAD_HANDLER, W_TERMINATE_OFFLOAD_HANDLER, ndischimney/MiniportTerminateOffload, tcp_chim_miniport_func_73171220-b803-4d9e-bf13-fe4daebbe5dc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndischimney.h
apiname:
-	MiniportTerminateOffload
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# W_TERMINATE_OFFLOAD_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportTerminateOffload</i> function terminates the offload of one or more state objects.


## -prototype


````
W_TERMINATE_OFFLOAD_HANDLER MiniportTerminateOffload;

VOID MiniportTerminateOffload(
  _In_    NDIS_HANDLE                       MiniportAdapterContext,
  _Inout_ PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
)
{ ... }
````


## -parameters




#### - MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <mshelp:link keywords="netvista.ndismsetminiportattributes" tabindex="0"><b>
     NdisMSetMiniportAttributes</b></mshelp:link> from its 
     <mshelp:link keywords="netvista.miniportinitializeex" tabindex="0"><i>
     MiniportInitializeEx</i></mshelp:link> function.


#### - OffloadBlockList [in, out]

A pointer to an 
     <mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state objects that are being terminated.


## -returns


None



## -remarks


The 
    <i>MiniportTerminateOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the terminate
    operation asynchronously by calling the 
    <mshelp:link keywords="netvista.ndismterminateoffloadcomplete" tabindex="0"><b>
    NdisMTerminateOffloadComplete</b></mshelp:link> function.

The 
    <i>OffloadBlockList</i> pointer points to an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that can be either
    a stand-alone structure or the root block list in an 
    <a href="https://msdn.microsoft.com/c96608bd-5e8f-499b-872a-b6f7f33c9e0c">offload state tree</a> that contains multiple
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. Such block lists, as well as any 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570939">offload state structures</a> that are
    associated with them, are valid until the miniport driver calls the 
    <b>NdisMTerminateOffloadComplete</b> function.

Each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure can be immediately followed in memory by a delegated
    state structure (<i>XXX</i>_OFFLOAD_STATE_DELEGATED). The offload target copies delegated variable values into the
    delegated state structures supplied by the host stack.

The host stack will not request the termination of the offload of a TCP connection until both of the
    following conditions are met:
<ul>
<li>
All the outstanding invalidate, query, and update requests pertaining to that connection have
      completed.

</li>
<li>
All outstanding receive and disconnect calls have returned.

</li>
</ul>


## -see-also

<mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<mshelp:link keywords="netvista.ndismterminateoffloadcomplete" tabindex="0"><b>
   NdisMTerminateOffloadComplete</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>

<a href="..\ndischimney\ns-ndischimney-_tcp_offload_state_delegated.md">TCP_OFFLOAD_STATE_DELEGATED</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20W_TERMINATE_OFFLOAD_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

