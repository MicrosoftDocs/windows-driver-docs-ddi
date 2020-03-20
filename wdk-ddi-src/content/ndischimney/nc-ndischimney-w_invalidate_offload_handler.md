---
UID: NC:ndischimney.W_INVALIDATE_OFFLOAD_HANDLER
title: W_INVALIDATE_OFFLOAD_HANDLER (ndischimney.h)
description: The MiniportInvalidateOffload function invalidates previously offloaded TCP chimney state objects.
old-location: netvista\miniportinvalidateoffload.htm
tech.root: netvista
ms.assetid: 58226149-daea-40aa-afb6-13ce615434b3
ms.date: 05/02/2018
keywords: ["W_INVALIDATE_OFFLOAD_HANDLER callback function"]
ms.keywords: MiniportInvalidateOffload, MiniportInvalidateOffload callback function [Network Drivers Starting with Windows Vista], W_INVALIDATE_OFFLOAD_HANDLER, W_INVALIDATE_OFFLOAD_HANDLER callback, ndischimney/MiniportInvalidateOffload, netvista.miniportinvalidateoffload, tcp_chim_miniport_func_226472dd-905a-42ef-8251-b32acfa93f0b.xml
f1_keywords:
 - "ndischimney/MiniportInvalidateOffload"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndischimney.h
api_name:
- MiniportInvalidateOffload
product:
- Windows
targetos: Windows
req.typenames: 
---

# W_INVALIDATE_OFFLOAD_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportInvalidateOffload</i> function invalidates previously offloaded TCP chimney state objects.


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state object that is being invalidated.


## -remarks



The 
    <i>MiniportInvalidateOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the invalidate
    operation asynchronously by calling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisminvalidateoffloadcomplete">
    NdisMInvalidateOffloadComplete</a>.

The tree passed to the 
    <i>MiniportInvalidateOffload</i> function contains only NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. The
    tree does not contain any 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">offload state structures</a>. That is,
    there are no such structures following the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in memory.

The NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in the tree indicate the state object to be
    invalidated. A non-NULL 
    <b>*MiniportOffloadContext</b> member points to a memory location containing a PVOID value that was
    supplied by the offload target when the state object was offloaded. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/storing-and-referencing-offloaded-state">Storing and Referencing
    Offloaded State</a>. This PVOID value references the miniport offload context in which the offload
    target stores the state object to be invalidated.

For information about an offload target's treatment of invalidated state objects, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/handling-invalidated-state-objects">Treatment of Invalidated State
    Objects</a>.

Eventually, the host stack will 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/terminating-offload-state">terminate the offload of the invalidated
    state object</a>. However, until that time, the offload target owns the invalidated state object. The
    offload target must not free the resources for the invalidated state object until the host stack has
    terminated the offload of that state object. The offload target must not use the invalidated state object
    or any TCP connections that depend on that state object for sending data.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisminvalidateoffloadcomplete">
   NdisMInvalidateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
 

 

