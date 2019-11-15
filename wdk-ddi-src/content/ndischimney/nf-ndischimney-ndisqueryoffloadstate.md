---
UID: NF:ndischimney.NdisQueryOffloadState
title: NdisQueryOffloadState function (ndischimney.h)
description: A protocol or intermediate driver calls the NdisQueryOffloadState function to query previously offloaded TCP chimney state objects.
old-location: netvista\ndisqueryoffload.htm
tech.root: netvista
ms.assetid: 97d30ba7-b67c-460b-ba80-171687495e27
ms.date: 05/02/2018
ms.keywords: NdisQueryOffloadState, NdisQueryOffloadState function [Network Drivers Starting with Windows Vista], ndis/NdisQueryOffloadState, netvista.ndisqueryoffload, tcp_chim_ndis_func_9075e6da-2950-4643-b626-36b4a9ce5a33.xml
ms.topic: function
f1_keywords:
 - "ndischimney/NdisQueryOffloadState"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisQueryOffloadState
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisQueryOffloadState function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol or intermediate driver calls the 
  <b>NdisQueryOffloadState</b> function to query previously offloaded TCP chimney state objects.


## -parameters




### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the offloaded state objects that are being
     queried.


## -remarks



An intermediate driver calls the 
    <b>NdisQueryOffloadState</b> function to propagate a query offload operation that was initiated by the host
    stack. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisqueryoffloadstate">Propagating
    State-Manipulation Operations</a>.

From the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_query_offload_handler">MiniportQueryOffload</a> function, the
    intermediate driver constructs an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. For more information, see
    Reusing an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> Structure. The intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure when calling the 
    <b>NdisQueryOffloadState</b> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_query_offload_handler">MiniportQueryOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_protocol_offload_block_list">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismqueryoffloadstatecomplete">
   NdisMQueryOffloadStateComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-query_offload_complete_handler">
   ProtocolQueryOffloadComplete</a>
 

 

