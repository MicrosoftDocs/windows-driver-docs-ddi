---
UID: NC:ndischimney.INITIATE_OFFLOAD_COMPLETE_HANDLER
title: INITIATE_OFFLOAD_COMPLETE_HANDLER (ndischimney.h)
description: NDIS calls a protocol driver's or intermediate driver's ProtocolInitiateOffloadComplete function to complete an offload operation that the driver previously initiated by calling the NdisInitiateOffload function.
old-location: netvista\protocolinitiateoffloadcomplete.htm
tech.root: netvista
ms.assetid: 0300d841-b211-42f8-b60d-d7d37201e778
ms.date: 05/02/2018
keywords: ["INITIATE_OFFLOAD_COMPLETE_HANDLER callback function"]
ms.keywords: INITIATE_OFFLOAD_COMPLETE_HANDLER, INITIATE_OFFLOAD_COMPLETE_HANDLER callback, ProtocolInitiateOffloadComplete, ProtocolInitiateOffloadComplete callback function [Network Drivers Starting with Windows Vista], ndischimney/ProtocolInitiateOffloadComplete, netvista.protocolinitiateoffloadcomplete, tcp_chim_protocol_func_24008ba0-91ac-43de-a1b7-ba82e15057ad.xml
f1_keywords:
 - "ndischimney/ProtocolInitiateOffloadComplete"
 - "ProtocolInitiateOffloadComplete"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndischimney.h
api_name:
- ProtocolInitiateOffloadComplete
targetos: Windows
req.typenames: 
---

# INITIATE_OFFLOAD_COMPLETE_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolInitiateOffloadComplete</i> function to complete an offload operation that the driver previously
  initiated by calling the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisinitiateoffload">NdisInitiateOffload</a> function.


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state that was offloaded or that was
     attempted to be offloaded.


## -remarks



In response to an underlying offload target's or intermediate driver's call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisminitiateoffloadcomplete">
    NdisMInitiateOffloadComplete</a> function, NDIS calls the overlying protocol's or intermediate driver's
    
    <i>ProtocolInitiateOffloadComplete</i> function.

An intermediate driver must propagate the completion of the initiate offload operation to the driver
    above it by calling 
    <b>NdisMInitiateOffloadComplete</b>. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/propagating-the-completion-of-a-state-manipulation-operation">
    Propagating the Completion of a State-Manipulation Operation</a>.

From the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <i>ProtocolInitiateOffloadComplete</i> function, the intermediate driver constructs an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/reusing-an-ndis-protocol-offload-block-list-structure">Reusing an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST Structure</a>. When calling the 
    <b>NdisMInitiateOffloadComplete</b> function, the intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this newly constructed NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_initiate_offload_handler">MiniportInitiateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisinitiateoffload">NdisInitiateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisminitiateoffloadcomplete">NdisMInitiateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>
 

 

