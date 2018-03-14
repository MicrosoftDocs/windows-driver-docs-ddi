---
UID: NF:ndischimney.NdisMOffloadEventIndicate
title: NdisMOffloadEventIndicate function
author: windows-driver-content
description: An offload target calls the NdisMOffloadEventIndicate function to indicate various events to the host stack.
old-location: netvista\ndismoffloadeventindicate.htm
old-project: netvista
ms.assetid: 81052e73-4dce-48df-8541-5da54e2156d8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMOffloadEventIndicate, NdisMOffloadEventIndicate function [Network Drivers Starting with Windows Vista], ndischimney/NdisMOffloadEventIndicate, netvista.ndismoffloadeventindicate, tcp_chim_ndis_func_6199452b-e2ea-41ca-8a16-eaf5109430fe.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	NdisMOffloadEventIndicate
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisMOffloadEventIndicate function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMOffloadEventIndicate</b> function to indicate various events to the host stack.


## -syntax


````
VOID NdisMOffloadEventIndicate(
  _In_ NDIS_HANDLE                       NdisMiniportHandle,
  _In_ PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList,
  _In_ ULONG                             IndicationCode
);
````


## -parameters




### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a>.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. This structure identifies the offloaded state object
     on which the indication is being made. Note that there is only one NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
     structure. There is not a linked list of such structures.
     

The offload target supplies a valid 
     <i>OffloadBlockList</i> pointer when making a 
     <b>NeighborReachabilityQuery</b> indication. In this case, the offload target supplies a 
     <a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_const.md">
     NEIGHBOR_OFFLOAD_STATE_CONST</a> structure, a 
     <a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_cached.md">
     NEIGHBOR_OFFLOAD_STATE_CACHED</a> structure, and a 
     <a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_delegated.md">
     NEIGHBOR_OFFLOAD_STATE_DELEGATED</a> structure (in that order) immediately following the
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure referenced by the 
     <i>OffloadBlockList</i> pointer.

An offload target must initialize the following members of an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
     structure that it passes to the 
     <b>NdisMOffloadEventIndicate</b> function:

<ul>
<li>
All members of the NDIS_OBJECT_HEADER structure, including 
       <b>Type</b>, 
       <b>Revision</b>, and 
       <b>Size</b> . The offload target must initialize 
       <b>Type</b> to 
       <b>NeighborOffloadState</b>.

</li>
<li>
The 
       <b>NextBlock</b> pointer to a non-<b>NULL</b> value if there is a next block; otherwise, to <b>NULL</b>.

</li>
<li>
The 
       <b>DependentBlockList</b> pointer to <b>NULL</b>.

</li>
<li>
The 
       <b>Status</b> member to NDIS_STATUS_SUCCESS.

</li>
</ul>
 The offload target does not have to initialize any other members of the
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure.
     

For all indications other than the 
     <b>NeighborReachabilityQuery</b> indication, the offload target supplies an 
     <i>OffloadBlockList</i> pointer that is <b>NULL</b>.


### -param IndicationCode [in]

The event being indicated is specified as one of the following INDICATE_OFFLOAD_EVENT values:
     





#### NeighborReachabilityQuery

Indicates that a neighbor cache entry (NCE) has become stale. For more information about NCEs,
       see RFC 2461.



#### NeighborReachabilityInDoubt

Reserved.


## -returns



None




## -remarks



The host stack uses the 
    <b>NeighborReachabilityQuery</b> indication to detect neighbor unreachability for IPv4 and IPv6. For a
    detailed description of this indication, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/making-a-neighborreachabilityquery-indication">Making a
    NeighborReachabilityQuery Indication</a>.




## -see-also

<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_delegated.md">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>



<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_const.md">NEIGHBOR_OFFLOAD_STATE_CONST</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_cached.md">NEIGHBOR_OFFLOAD_STATE_CACHED</a>



<a href="..\ndischimney\nc-ndischimney-w_initiate_offload_handler.md">MiniportInitiateOffload</a>



<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>



 

 


