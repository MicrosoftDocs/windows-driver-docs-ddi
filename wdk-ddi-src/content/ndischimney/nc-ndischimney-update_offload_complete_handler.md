---
UID: NC:ndischimney.UPDATE_OFFLOAD_COMPLETE_HANDLER
title: UPDATE_OFFLOAD_COMPLETE_HANDLER (ndischimney.h)
description: NDIS calls a protocol driver's or intermediate driver's ProtocolUpdateOffloadComplete function to complete an update offload operation that the driver previously initiated by calling the NdisUpdateOffload function.
old-location: netvista\protocolupdateoffloadcomplete.htm
tech.root: netvista
ms.assetid: 3cd7a32a-d560-429b-b191-aeabb87433f3
ms.date: 05/02/2018
ms.keywords: ProtocolUpdateOffloadComplete, ProtocolUpdateOffloadComplete callback function [Network Drivers Starting with Windows Vista], UPDATE_OFFLOAD_COMPLETE_HANDLER, UPDATE_OFFLOAD_COMPLETE_HANDLER callback, ndischimney/ProtocolUpdateOffloadComplete, netvista.protocolupdateoffloadcomplete, tcp_chim_protocol_func_dd66a468-9cad-4763-8eea-f7502811368e.xml
ms.topic: callback
f1_keywords:
 - "ndischimney/ProtocolUpdateOffloadComplete"
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
- ProtocolUpdateOffloadComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# UPDATE_OFFLOAD_COMPLETE_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolUpdateOffloadComplete</i> function to complete an update offload operation that the driver
  previously initiated by calling the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisupdateoffload">NdisUpdateOffload</a> function.


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state that was updated or that was
     attempted to be updated.


## -returns



None




## -remarks



In response to an underlying offload target's or intermediate driver's call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismupdateoffloadcomplete">
    NdisMUpdateOffloadComplete</a> function, NDIS calls a protocol or intermediate driver's 
    <i>ProtocolUpdateOffloadComplete</i> function.

An intermediate driver must propagate the completion of the update offload operation to the driver
    above it by calling 
    <b>NdisMUpdateOffloadComplete</b>. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/propagating-the-completion-of-a-state-manipulation-operation">
    Propagating the Completion of a State-Manipulation Operation</a>.

From the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <i>ProtocolUpdateOffloadComplete</i> function, the intermediate driver constructs an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/reusing-an-ndis-protocol-offload-block-list-structure">Reusing an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST Structure</a>. When calling the 
    <b>NdisMUpdateOffloadComplete</b> function, the intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this newly constructed NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_update_offload_handler">MiniportUpdateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismupdateoffloadcomplete">NdisMUpdateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisupdateoffload">NdisUpdateOffload</a>
 

 

