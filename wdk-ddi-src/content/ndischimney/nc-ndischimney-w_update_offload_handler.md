---
UID: NC:ndischimney.W_UPDATE_OFFLOAD_HANDLER
title: W_UPDATE_OFFLOAD_HANDLER (ndischimney.h)
description: The MiniportUpdateOffload function updates previously offloaded TCP chimney state objects.
old-location: netvista\miniportupdateoffload.htm
tech.root: netvista
ms.assetid: b98b2e21-8b28-4da0-9cc9-6fa8cb6e5be7
ms.date: 05/02/2018
ms.keywords: MiniportUpdateOffload, MiniportUpdateOffload callback function [Network Drivers Starting with Windows Vista], W_UPDATE_OFFLOAD_HANDLER, W_UPDATE_OFFLOAD_HANDLER callback, ndischimney/MiniportUpdateOffload, netvista.miniportupdateoffload, tcp_chim_miniport_func_e6dbcab7-ff44-46c0-ae03-729ea479d13c.xml
ms.topic: callback
f1_keywords:
 - "ndischimney/MiniportUpdateOffload"
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
- MiniportUpdateOffload
product:
- Windows
targetos: Windows
req.typenames: 
---

# W_UPDATE_OFFLOAD_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportUpdateOffload</i> function updates previously offloaded TCP chimney state objects.


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload target-allocated context area in which the offload target maintains state
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
     structures. These structures identify the offloaded state objects that are being updated. Only cached
     variables are updated.


## -returns



None




## -remarks



Only cached variables are updated.

The 
    <i>MiniportUpdateOffload</i> function stores the 
    <i>MiniportAdapterContext</i> handle and the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the update operation
    asynchronously by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismupdateoffloadcomplete">
    NdisMUpdateOffloadComplete</a> function. The 
    <i>OffloadBlockList</i> pointer points to an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that can either be
    a stand-alone structure or the root block list in an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/offload-state-tree">offload state tree</a> that contains multiple
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. Such block lists, as well as any 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">offload state structures</a> that are
    associated with them, are valid until the miniport driver calls the 
    <b>
    NdisMUpdateOffloadComplete</b> function.

Before the 
    <i>MiniportUpdateOffload</i> function returns, the offload target uses the offload state tree passed to
    the 
    <i>MiniportUpdateOffload</i> function to update offloaded state:

<ul>
<li>
The offload target copies the variable values from any state structures in the tree to the
      corresponding 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/offload-state-objects">offloaded state objects</a>. Only CACHED
      variables are updated.

</li>
<li>
The tree might indicate that path-to-neighbor links must be updated. For more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_update_offload_handler">Linking
      Path State Objects to a New Neighbor State Object</a>. In this case, the offload target must update
      its internal representation of offloaded state to reflect the updated links.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismupdateoffloadcomplete">NdisMUpdateOffloadComplete</a>
 

 

