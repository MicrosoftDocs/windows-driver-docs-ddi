---
UID: NC:ndischimney.W_TERMINATE_OFFLOAD_HANDLER
title: W_TERMINATE_OFFLOAD_HANDLER (ndischimney.h)
description: The MiniportTerminateOffload function terminates the offload of one or more state objects.
old-location: netvista\miniportterminateoffload.htm
tech.root: netvista
ms.assetid: 1b808e3c-2d64-44c9-88d3-0a0311e1dc99
ms.date: 05/02/2018
keywords: ["W_TERMINATE_OFFLOAD_HANDLER callback function"]
ms.keywords: MiniportTerminateOffload, MiniportTerminateOffload callback function [Network Drivers Starting with Windows Vista], W_TERMINATE_OFFLOAD_HANDLER, W_TERMINATE_OFFLOAD_HANDLER callback, ndischimney/MiniportTerminateOffload, netvista.miniportterminateoffload, tcp_chim_miniport_func_73171220-b803-4d9e-bf13-fe4daebbe5dc.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - W_TERMINATE_OFFLOAD_HANDLER
 - ndischimney/W_TERMINATE_OFFLOAD_HANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndischimney.h
api_name:
 - MiniportTerminateOffload
---

# W_TERMINATE_OFFLOAD_HANDLER callback function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportTerminateOffload</i> function terminates the offload of one or more state objects.

## -parameters

### -param MiniportAdapterContext 

[in]
The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
     NdisMSetMiniportAttributes</a> from its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.

### -param OffloadBlockList 

[in, out]
A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state objects that are being terminated.

## -remarks

The 
    <i>MiniportTerminateOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the terminate
    operation asynchronously by calling the 
    <a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismterminateoffloadcomplete">
    NdisMTerminateOffloadComplete</a> function.

The 
    <i>OffloadBlockList</i> pointer points to an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that can be either
    a stand-alone structure or the root block list in an 
    <a href="/windows-hardware/drivers/network/offload-state-tree">offload state tree</a> that contains multiple
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. Such block lists, as well as any 
    <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">offload state structures</a> that are
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

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismterminateoffloadcomplete">
   NdisMTerminateOffloadComplete</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">TCP_OFFLOAD_STATE_DELEGATED</a>