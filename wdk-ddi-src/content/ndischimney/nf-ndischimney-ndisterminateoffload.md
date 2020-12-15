---
UID: NF:ndischimney.NdisTerminateOffload
title: NdisTerminateOffload function (ndischimney.h)
description: A protocol driver or intermediate driver calls the NdisTerminateOffload function to terminate the offload of one or more state objects
old-location: netvista\ndisterminateoffload.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisTerminateOffload function"]
ms.keywords: NdisTerminateOffload, NdisTerminateOffload function [Network Drivers Starting with Windows Vista], ndischimney/NdisTerminateOffload, netvista.ndisterminateoffload, tcp_chim_ndis_func_44201f08-cbfc-4796-b2a9-78bbc5c348c4.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisTerminateOffload
 - ndischimney/NdisTerminateOffload
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisTerminateOffload
---

# NdisTerminateOffload function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or intermediate driver calls the 
  <b>NdisTerminateOffload</b> function to terminate the offload of one or more state objects

## -parameters

### -param NdisBindingHandle 

[in]
The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.

### -param OffloadBlockList 

[in, out]
A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the offloaded state objects that are being
     terminated.

## -remarks

An intermediate driver calls the 
    <b>NdisTerminateOffload</b> function to propagate a terminate offload operation that was initiated by the
    host stack. For more information, see 
    <a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisqueryoffloadstate">Propagating
    State-Manipulation Operations</a>.

From the 
    <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that was passed to its 
    <i>MiniportTerminateOffload</i> function, the intermediate driver constructs an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. For more information, see 
    <a href="/windows-hardware/drivers/network/reusing-an-ndis-miniport-offload-block-list-structure">Reusing an
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST Structure</a>. The intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure when calling the 
    <b>NdisTerminateOffload</b> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_terminate_offload_handler">MiniportTerminateOffload</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismterminateoffloadcomplete">
   NdisMTerminateOffloadComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-terminate_offload_complete_handler">
   ProtocolTerminateOffloadComplete</a>
