---
UID: NF:ndischimney.NdisQueryOffloadState
title: NdisQueryOffloadState function
author: windows-driver-content
description: A protocol or intermediate driver calls the NdisQueryOffloadState function to query previously offloaded TCP chimney state objects.
old-location: netvista\ndisqueryoffload.htm
old-project: netvista
ms.assetid: 97d30ba7-b67c-460b-ba80-171687495e27
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisQueryOffloadState, NdisQueryOffloadState function [Network Drivers Starting with Windows Vista], ndis/NdisQueryOffloadState, netvista.ndisqueryoffload, tcp_chim_ndis_func_9075e6da-2950-4643-b626-36b4a9ce5a33.xml
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisQueryOffloadState
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisQueryOffloadState function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol or intermediate driver calls the 
  <b>NdisQueryOffloadState</b> function to query previously offloaded TCP chimney state objects.


## -syntax


````
VOID NdisQueryOffloadState(
  _In_ NDIS_HANDLE                       NdisBindingHandle,
  _In_ PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST OffloadBlockList
);
````


## -parameters




### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_protocol_offload_block_list.md">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the offloaded state objects that are being
     queried.


## -returns



None




## -remarks



An intermediate driver calls the 
    <b>NdisQueryOffloadState</b> function to propagate a query offload operation that was initiated by the host
    stack. For more information, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff563771">Propagating
    State-Manipulation Operations</a>.

From the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a> function, the
    intermediate driver constructs an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. For more information, see
    Reusing an 
    <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> Structure. The intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure when calling the 
    <b>NdisQueryOffloadState</b> function.




## -see-also

<a href="..\ndischimney\nc-ndischimney-query_offload_complete_handler.md">
   ProtocolQueryOffloadComplete</a>



<a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_protocol_offload_block_list.md">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="..\ndischimney\nf-ndischimney-ndismqueryoffloadstatecomplete.md">
   NdisMQueryOffloadStateComplete</a>



 

 


