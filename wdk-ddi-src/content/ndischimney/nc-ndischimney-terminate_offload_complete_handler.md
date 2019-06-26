---
UID: NC:ndischimney.TERMINATE_OFFLOAD_COMPLETE_HANDLER
title: TERMINATE_OFFLOAD_COMPLETE_HANDLER (ndischimney.h)
description: NDIS calls a protocol or intermediate driver's ProtocolTerminateOffloadComplete function to complete a terminate offload operation that the driver previously initiated by calling the NdisTerminateOffload function.
old-location: netvista\protocolterminateoffloadcomplete.htm
tech.root: netvista
ms.assetid: 614d36e8-38ac-49a7-8711-7a6c6646309c
ms.date: 05/02/2018
ms.keywords: ProtocolTerminateOffloadComplete, ProtocolTerminateOffloadComplete callback function [Network Drivers Starting with Windows Vista], TERMINATE_OFFLOAD_COMPLETE_HANDLER, TERMINATE_OFFLOAD_COMPLETE_HANDLER callback, ndischimney/ProtocolTerminateOffloadComplete, netvista.protocolterminateoffloadcomplete, tcp_chim_protocol_func_77bcd97e-dea4-41e4-aae5-3aef1a616a45.xml
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndischimney.h
api_name:
- ProtocolTerminateOffloadComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# TERMINATE_OFFLOAD_COMPLETE_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTerminateOffloadComplete</i> function to complete a terminate offload operation that the driver
  previously initiated by calling the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndisterminateoffload">NdisTerminateOffload</a> function.


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state that was terminated or that was
     attempted to be terminated.


## -returns



None




## -remarks



In response to an underlying offload target's or intermediate driver's call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismterminateoffloadcomplete">
    NdisMTerminateOffloadComplete</a> function, NDIS calls a protocol or intermediate driver's 
    <i>ProtocolTerminateOffloadComplete</i> function.

An intermediate driver must propagate the completion of the terminate offload operation to the driver
    above it by calling 
    <b>NdisMTerminateOffloadComplete</b>. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/propagating-the-completion-of-a-state-manipulation-operation">
    Propagating the Completion of a State-Manipulation Operation</a>.

From the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <i>ProtocolTerminateOffloadComplete</i> function, the intermediate driver constructs an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/reusing-an-ndis-protocol-offload-block-list-structure">Reusing an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST Structure</a>. When calling the 
    <b>NdisMTerminateOffloadComplete</b> function, the intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this newly constructed NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_terminate_offload_handler">MiniportTerminateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismterminateoffloadcomplete">
   NdisMTerminateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndisterminateoffload">NdisTerminateOffload</a>
 

 

