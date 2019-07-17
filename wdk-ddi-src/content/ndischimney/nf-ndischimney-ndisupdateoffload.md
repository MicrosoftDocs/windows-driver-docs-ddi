---
UID: NF:ndischimney.NdisUpdateOffload
title: NdisUpdateOffload function (ndischimney.h)
description: A protocol or intermediate driver calls the NdisUpdateOffload function to update previously offloaded TCP chimney state objects.
old-location: netvista\ndisupdateoffload.htm
tech.root: netvista
ms.assetid: 1e85357d-9fe2-406b-bc1a-69e4357a0f8b
ms.date: 05/02/2018
ms.keywords: NdisUpdateOffload, NdisUpdateOffload function [Network Drivers Starting with Windows Vista], ndischimney/NdisUpdateOffload, netvista.ndisupdateoffload, tcp_chim_ndis_func_e33474cc-f963-48b8-8122-14f78bceb38f.xml
ms.topic: function
f1_keywords:
 - "ndischimney/NdisUpdateOffload"
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisUpdateOffload
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisUpdateOffload function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol or intermediate driver calls the 
  <b>NdisUpdateOffload</b> function to update previously offloaded TCP chimney state objects.


## -parameters




### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the offloaded state objects that are being
     updated.


## -returns



None




## -remarks



An intermediate driver calls the 
    <b>NdisUpdateOffload</b> function to propagate an update offload operation that was initiated by the host
    stack. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndisqueryoffloadstate">Propagating
    State-Manipulation Operations</a>.

From the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that was passed to its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_update_offload_handler">MiniportUpdateOffload</a> function,
    the intermediate driver constructs an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. For more information,
    see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/reusing-an-ndis-miniport-offload-block-list-structure">Reusing an
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST Structure</a>. The intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure when calling the 
    <b>NdisUpdateOffload</b> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_update_offload_handler">MiniportUpdateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismupdateoffloadcomplete">NdisMUpdateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-update_offload_complete_handler">
   ProtocolUpdateOffloadComplete</a>
 

 

