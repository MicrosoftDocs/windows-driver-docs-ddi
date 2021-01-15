---
UID: NC:ndischimney.QUERY_OFFLOAD_COMPLETE_HANDLER
title: QUERY_OFFLOAD_COMPLETE_HANDLER (ndischimney.h)
description: NDIS calls a protocol driver's or intermediate driver's ProtocolQueryOffloadComplete function to complete a query offload operation that the driver previously initiated by calling the NdisQueryOffload function.
old-location: netvista\protocolqueryoffloadcomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["QUERY_OFFLOAD_COMPLETE_HANDLER callback function"]
ms.keywords: ProtocolQueryOffloadComplete, ProtocolQueryOffloadComplete callback function [Network Drivers Starting with Windows Vista], QUERY_OFFLOAD_COMPLETE_HANDLER, QUERY_OFFLOAD_COMPLETE_HANDLER callback, ndischimney/ProtocolQueryOffloadComplete, netvista.protocolqueryoffloadcomplete, tcp_chim_protocol_func_044230e2-8c5e-4f7c-8f6c-5b7ba8f48810.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - QUERY_OFFLOAD_COMPLETE_HANDLER
 - ndischimney/QUERY_OFFLOAD_COMPLETE_HANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndischimney.h
api_name:
 - QUERY_OFFLOAD_COMPLETE_HANDLER
---

# QUERY_OFFLOAD_COMPLETE_HANDLER callback function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolQueryOffloadComplete</i> function to complete a query offload operation that the driver
  previously initiated by calling the 
  <a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisqueryoffloadstate">NdisQueryOffload</a> function.

## -parameters

### -param ProtocolBindingContext 

[in]
A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.

### -param OffloadBlockList 

[in]
A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state that was queried or that was
     attempted to be queried.

## -remarks

In response to an underlying offload target's or intermediate driver's call to the 
    <a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismqueryoffloadstatecomplete">
    NdisMQueryOffloadStateComplete</a> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolQueryOffloadComplete</i> function.

An intermediate driver must propagate the completion of the query offload operation to the driver
    above it by calling 
    <b>NdisMQueryOffloadStateComplete</b>. For more information, see 
    <a href="/windows-hardware/drivers/network/propagating-the-completion-of-a-state-manipulation-operation">
    Propagating the Completion of a State-Manipulation Operation</a>.

From the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <i>ProtocolQueryOffloadComplete</i> function, the intermediate driver constructs an 
    <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. For more information, see 
    <a href="/windows-hardware/drivers/network/reusing-an-ndis-protocol-offload-block-list-structure">Reusing an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST Structure</a>. When calling the 
    <b>NdisMQueryOffloadStateComplete</b> function, the intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this newly constructed NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_query_offload_handler">MiniportQueryOffload</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismqueryoffloadstatecomplete">
   NdisMQueryOffloadStateComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisqueryoffloadstate">NdisQueryOffload</a>

