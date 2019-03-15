---
UID: NC:ndischimney.INDICATE_OFFLOAD_EVENT_HANDLER
title: INDICATE_OFFLOAD_EVENT_HANDLER (ndischimney.h)
description: NDIS calls a protocol driver's or intermediate driver's ProtocolIndicateOffloadEvent function to post an indication that was initiated by an underlying driver's or offload target's call to the NdisMOffloadEventIndicate function.
old-location: netvista\protocolindicateoffloadevent.htm
tech.root: netvista
ms.assetid: 608c1c7c-1eb3-4d86-9471-313fce2df00e
ms.date: 05/02/2018
ms.keywords: INDICATE_OFFLOAD_EVENT_HANDLER, INDICATE_OFFLOAD_EVENT_HANDLER callback, ProtocolIndicateOffloadEvent, ProtocolIndicateOffloadEvent callback function [Network Drivers Starting with Windows Vista], ndischimney/ProtocolIndicateOffloadEvent, netvista.protocolindicateoffloadevent, tcp_chim_protocol_func_cc94798f-b74a-45d5-b78f-383698003486.xml
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
- ProtocolIndicateOffloadEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# INDICATE_OFFLOAD_EVENT_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolIndicateOffloadEvent</i> function to post an indication that was initiated by an underlying
  driver's or offload target's call to the 
  <a href="https://msdn.microsoft.com/81052e73-4dce-48df-8541-5da54e2156d8">
  NdisMOffloadEventIndicate</a> function.


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area that was allocated by the protocol driver. The driver maintains the per
     binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/64febd55-1ab8-4e2e-b738-340167866333">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure. This structure identifies the offloaded state object
     on which the indication is being made. Note that there is only one NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
     structure. There is not a linked list of such structures. 
     

The underlying offload target supplies a valid 
     <i>OffloadBlockList</i> pointer when making a 
     <b>NeighborReachabilityQuery</b> indication. In this case, the offload target supplies a 
     <a href="https://msdn.microsoft.com/1c79a3d6-c365-4740-a2e0-94333b70d8cc">
     NEIGHBOR_OFFLOAD_STATE_CONST</a> structure, a 
     <a href="https://msdn.microsoft.com/5dedffa8-9745-4668-8646-0e896942b9c8">
     NEIGHBOR_OFFLOAD_STATE_CACHED</a> structure, and a 
     <a href="https://msdn.microsoft.com/94a35d0f-3585-45d0-bba8-0b4a8ebbe883">
     NEIGHBOR_OFFLOAD_STATE_DELEGATED</a> structure (in that order) immediately following the
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure referenced by the 
     <i>OffloadBlockList</i> pointer.


### -param IndicationCode [in]

The event being indicated as one of the following INDICATE_OFFLOAD_EVENT values:
     





#### NeighborReachabilityQuery

Indicates that a neighbor cache entry (NCE) has become stale. For more information about NCEs,
       see RFC 2461.



#### NeighborReachabilityInDoubt

Reserved.


## -returns



None




## -remarks



The implementation of this function for intermediate drivers is to be determined.




## -see-also




<a href="https://msdn.microsoft.com/64febd55-1ab8-4e2e-b738-340167866333">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568323">NEIGHBOR_OFFLOAD_STATE_CACHED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568324">NEIGHBOR_OFFLOAD_STATE_CONST</a>



<a href="https://msdn.microsoft.com/94a35d0f-3585-45d0-bba8-0b4a8ebbe883">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563619">NdisMOffloadEventIndicate</a>
 

 

