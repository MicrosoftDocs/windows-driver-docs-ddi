---
UID: NC:ndischimney.W_QUERY_OFFLOAD_HANDLER
title: W_QUERY_OFFLOAD_HANDLER (ndischimney.h)
description: The MiniportQueryOffload function queries previously offloaded TCP chimney state objects.
old-location: netvista\miniportqueryoffload.htm
tech.root: netvista
ms.assetid: a583c4cb-53c1-4eff-bcfe-c962f736b1f8
ms.date: 05/02/2018
ms.keywords: MiniportQueryOffload, MiniportQueryOffload callback function [Network Drivers Starting with Windows Vista], W_QUERY_OFFLOAD_HANDLER, W_QUERY_OFFLOAD_HANDLER callback, ndischimney/MiniportQueryOffload, netvista.miniportqueryoffload, tcp_chim_miniport_func_920f9145-1dda-4899-85d7-845dd545a6bc.xml
f1_keywords:
 - "ndischimney/MiniportQueryOffload"
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
- MiniportQueryOffload
product:
- Windows
targetos: Windows
req.typenames: 
---

# W_QUERY_OFFLOAD_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportQueryOffload</i> function queries previously offloaded TCP chimney state objects.


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param OffloadBlockList [in, out]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state that is being queried.


## -remarks



The 
    <i>MiniportQueryOffload</i> function can query any TCP chimney state that has been offloaded to the
    offload target.

The 
    <i>MiniportQueryOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the query operation
    asynchronously by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismqueryoffloadstatecomplete">
    NdisMQueryOffloadStateComplete</a> function. The 
    <i>OffloadBlockList</i> pointer points to an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that can either be a stand-alone structure or the root
    node in an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/offload-state-tree">offload state tree</a>. The state tree is valid
    until the offload target calls the 
    <b>NdisMQueryOffloadStateComplete</b> function.

After returning from the 
    <i>MiniportQueryOffload</i> function, the miniport driver fills in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">offload state structure</a> that is
    associated with each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree pointed to by the 
    <i>OffloadBlockList</i> pointer. To each of these offload state structures, the miniport driver writes the
    current value of each variable in the structure.

Before calling the 
    <b>NdisMQueryOffloadStateComplete</b> function, the offload target must write either of the following
    NDIS_STATUS values to the 
    <b>Status</b> member of each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree:

<ul>
<li>
NDIS_STATUS_SUCCESS
     

The offload target successfully queried the state objects.

</li>
<li>
NDIS_STATUS_FAILURE
     

The query operation did not succeed. The host stack will terminate the state objects that could not
     be queried.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismqueryoffloadstatecomplete">
   NdisMQueryOffloadStateComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
 

 

