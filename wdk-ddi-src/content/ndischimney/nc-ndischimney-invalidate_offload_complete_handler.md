---
UID: NC:ndischimney.INVALIDATE_OFFLOAD_COMPLETE_HANDLER
title: INVALIDATE_OFFLOAD_COMPLETE_HANDLER (ndischimney.h)
description: NDIS calls a protocol driver's or intermediate driver's ProtocolInvalidateOffloadComplete function to complete an invalidate operation that the driver previously initiated by calling the NdisInvalidateOffload function.
old-location: netvista\protocolinvalidateoffloadcomplete.htm
tech.root: netvista
ms.assetid: 6d2c71d0-9686-4eb5-9715-27de3dc8b390
ms.date: 05/02/2018
ms.keywords: INVALIDATE_OFFLOAD_COMPLETE_HANDLER, INVALIDATE_OFFLOAD_COMPLETE_HANDLER callback, ProtocolInvalidateOffloadComplete, ProtocolInvalidateOffloadComplete callback function [Network Drivers Starting with Windows Vista], ndischimney/ProtocolInvalidateOffloadComplete, netvista.protocolinvalidateoffloadcomplete, tcp_chim_protocol_func_af2a329a-730b-4ccb-afc6-702e88a763f2.xml
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
- ProtocolInvalidateOffloadComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# INVALIDATE_OFFLOAD_COMPLETE_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolInvalidateOffloadComplete</i> function to complete an invalidate operation that the driver
  previously initiated by calling the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff562774">NdisInvalidateOffload</a> function.


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/64febd55-1ab8-4e2e-b738-340167866333">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state that was invalidated or that was
     attempted to be invalidated.


## -returns



None




## -remarks



In response to an underlying offload target's or intermediate driver's call to the 
    <a href="https://msdn.microsoft.com/fd14e983-ea4b-41f2-973d-88b114306e75">
    NdisMInvalidateOffloadComplete</a> function, NDIS calls the overlying protocol or intermediate driver's    
    <i>ProtocolInvalidateOffloadComplete</i> function.

An intermediate driver must propagate the completion of the initiate offload operation to the driver
    above it by calling 
    <b>NdisMInvalidateOffloadComplete</b>. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/propagating-the-completion-of-a-state-manipulation-operation">
    Propagating the Completion of a State-Manipulation Operation</a>.

From the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <i>ProtocolInvalidateOffloadComplete</i> function, the intermediate driver constructs an 
    <a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/reusing-an-ndis-protocol-offload-block-list-structure">Reusing an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST Structure</a>. When calling the 
    <b>NdisMInvalidateOffloadComplete</b> function, the intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this newly constructed NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure.




## -see-also




<a href="https://msdn.microsoft.com/58226149-daea-40aa-afb6-13ce615434b3">MiniportInvalidateOffload</a>



<a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://msdn.microsoft.com/64febd55-1ab8-4e2e-b738-340167866333">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562774">NdisInvalidateOffload</a>



<a href="https://msdn.microsoft.com/fd14e983-ea4b-41f2-973d-88b114306e75">
   NdisMInvalidateOffloadComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
 

 

