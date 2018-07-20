---
UID: NC:ndischimney.W_INVALIDATE_OFFLOAD_HANDLER
title: W_INVALIDATE_OFFLOAD_HANDLER
author: windows-driver-content
description: The MiniportInvalidateOffload function invalidates previously offloaded TCP chimney state objects.
old-location: netvista\miniportinvalidateoffload.htm
tech.root: netvista
ms.assetid: 58226149-daea-40aa-afb6-13ce615434b3
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: MiniportInvalidateOffload, MiniportInvalidateOffload callback function [Network Drivers Starting with Windows Vista], W_INVALIDATE_OFFLOAD_HANDLER, W_INVALIDATE_OFFLOAD_HANDLER callback, ndischimney/MiniportInvalidateOffload, netvista.miniportinvalidateoffload, tcp_chim_miniport_func_226472dd-905a-42ef-8251-b32acfa93f0b.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndischimney.h
api_name:
-	MiniportInvalidateOffload
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
     <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state object that is being invalidated.


## -returns



None




## -remarks



The 
    <i>MiniportInvalidateOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the invalidate
    operation asynchronously by calling 
    <a href="https://msdn.microsoft.com/fd14e983-ea4b-41f2-973d-88b114306e75">
    NdisMInvalidateOffloadComplete</a>.

The tree passed to the 
    <i>MiniportInvalidateOffload</i> function contains only NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. The
    tree does not contain any 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570939">offload state structures</a>. That is,
    there are no such structures following the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in memory.

The NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in the tree indicate the state object to be
    invalidated. A non-NULL 
    <b>*MiniportOffloadContext</b> member points to a memory location containing a PVOID value that was
    supplied by the offload target when the state object was offloaded. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/storing-and-referencing-offloaded-state">Storing and Referencing
    Offloaded State</a>. This PVOID value references the miniport offload context in which the offload
    target stores the state object to be invalidated.

For information about an offload target's treatment of invalidated state objects, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/handling-invalidated-state-objects">Treatment of Invalidated State
    Objects</a>.

Eventually, the host stack will 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/terminating-offload-state">terminate the offload of the invalidated
    state object</a>. However, until that time, the offload target owns the invalidated state object. The
    offload target must not free the resources for the invalidated state object until the host stack has
    terminated the offload of that state object. The offload target must not use the invalidated state object
    or any TCP connections that depend on that state object for sending data.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://msdn.microsoft.com/fd14e983-ea4b-41f2-973d-88b114306e75">
   NdisMInvalidateOffloadComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
 

 

