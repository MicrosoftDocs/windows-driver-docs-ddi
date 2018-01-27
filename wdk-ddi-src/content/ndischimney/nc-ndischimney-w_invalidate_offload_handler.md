---
UID: NC:ndischimney.W_INVALIDATE_OFFLOAD_HANDLER
title: W_INVALIDATE_OFFLOAD_HANDLER
author: windows-driver-content
description: The MiniportInvalidateOffload function invalidates previously offloaded TCP chimney state objects.
old-location: netvista\miniportinvalidateoffload.htm
old-project: netvista
ms.assetid: 58226149-daea-40aa-afb6-13ce615434b3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportinvalidateoffload, MiniportInvalidateOffload callback function [Network Drivers Starting with Windows Vista], MiniportInvalidateOffload, W_INVALIDATE_OFFLOAD_HANDLER, W_INVALIDATE_OFFLOAD_HANDLER, ndischimney/MiniportInvalidateOffload, tcp_chim_miniport_func_226472dd-905a-42ef-8251-b32acfa93f0b.xml
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
-	MiniportInvalidateOffload
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# W_INVALIDATE_OFFLOAD_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportInvalidateOffload</i> function invalidates previously offloaded TCP chimney state objects.


## -prototype


````
W_INVALIDATE_OFFLOAD_HANDLER MiniportInvalidateOffload;

VOID MiniportInvalidateOffload(
  _In_ NDIS_HANDLE                       MiniportAdapterContext,
  _In_ PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <mshelp:link keywords="netvista.ndismsetminiportattributes" tabindex="0"><b>
     NdisMSetMiniportAttributes</b></mshelp:link> from its 
     <mshelp:link keywords="netvista.miniportinitializeex" tabindex="0"><i>
     MiniportInitializeEx</i></mshelp:link> function.


### -param OffloadBlockList [in]

A pointer to an 
     <mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state object that is being invalidated.


## -returns


None



## -remarks


The 
    <i>MiniportInvalidateOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the invalidate
    operation asynchronously by calling 
    <mshelp:link keywords="netvista.ndisminvalidateoffloadcomplete" tabindex="0"><b>
    NdisMInvalidateOffloadComplete</b></mshelp:link>.

The tree passed to the 
    <i>MiniportInvalidateOffload</i> function contains only NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. The
    tree does not contain any 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570939">offload state structures</a>. That is,
    there are no such structures following the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in memory.

The NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in the tree indicate the state object to be
    invalidated. A non-NULL 
    <b>*MiniportOffloadContext</b> member points to a memory location containing a PVOID value that was
    supplied by the offload target when the state object was offloaded. For more information, see 
    <mshelp:link keywords="netvista.storing_and_referencing_offloaded_state" tabindex="0">Storing and Referencing
    Offloaded State</mshelp:link>. This PVOID value references the miniport offload context in which the offload
    target stores the state object to be invalidated.

For information about an offload target's treatment of invalidated state objects, see 
    <mshelp:link keywords="netvista.handling_invalidated_state_objects" tabindex="0">Treatment of Invalidated State
    Objects</mshelp:link>.

Eventually, the host stack will 
    <mshelp:link keywords="netvista.terminating_offload_state" tabindex="0">terminate the offload of the invalidated
    state object</mshelp:link>. However, until that time, the offload target owns the invalidated state object. The
    offload target must not free the resources for the invalidated state object until the host stack has
    terminated the offload of that state object. The offload target must not use the invalidated state object
    or any TCP connections that depend on that state object for sending data.



## -see-also

<mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<mshelp:link keywords="netvista.ndisminvalidateoffloadcomplete" tabindex="0"><b>
   NdisMInvalidateOffloadComplete</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20W_INVALIDATE_OFFLOAD_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

