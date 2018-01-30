---
UID: NC:ndischimney.TERMINATE_OFFLOAD_COMPLETE_HANDLER
title: TERMINATE_OFFLOAD_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol or intermediate driver's ProtocolTerminateOffloadComplete function to complete a terminate offload operation that the driver previously initiated by calling the NdisTerminateOffload function.
old-location: netvista\protocolterminateoffloadcomplete.htm
old-project: netvista
ms.assetid: 614d36e8-38ac-49a7-8711-7a6c6646309c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.protocolterminateoffloadcomplete, ProtocolTerminateOffloadComplete callback function [Network Drivers Starting with Windows Vista], ProtocolTerminateOffloadComplete, TERMINATE_OFFLOAD_COMPLETE_HANDLER, TERMINATE_OFFLOAD_COMPLETE_HANDLER, ndischimney/ProtocolTerminateOffloadComplete, tcp_chim_protocol_func_77bcd97e-dea4-41e4-aae5-3aef1a616a45.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndischimney.h
apiname:
-	ProtocolTerminateOffloadComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# TERMINATE_OFFLOAD_COMPLETE_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTerminateOffloadComplete</i> function to complete a terminate offload operation that the driver
  previously initiated by calling the 
  <a href="..\ndischimney\nf-ndischimney-ndisterminateoffload.md">NdisTerminateOffload</a> function.


## -prototype


````
TERMINATE_OFFLOAD_COMPLETE_HANDLER ProtocolTerminateOffloadComplete;

VOID ProtocolTerminateOffloadComplete(
  _In_ NDIS_HANDLE                       ProtocolBindingContext,
  _In_ PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST OffloadBlockList
)
{ ... }
````


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <mshelp:link keywords="netvista.ndis_protocol_offload_block_list" tabindex="0"><b>
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</b></mshelp:link> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state that was terminated or that was
     attempted to be terminated.


## -returns


None



## -remarks


In response to an underlying offload target's or intermediate driver's call to the 
    <mshelp:link keywords="netvista.ndismterminateoffloadcomplete" tabindex="0"><b>
    NdisMTerminateOffloadComplete</b></mshelp:link> function, NDIS calls a protocol or intermediate driver's 
    <i>ProtocolTerminateOffloadComplete</i> function.

An intermediate driver must propagate the completion of the terminate offload operation to the driver
    above it by calling 
    <b>NdisMTerminateOffloadComplete</b>. For more information, see 
    <mshelp:link keywords="netvista.propagating_the_completion_of_a_state_manipulation_operation" tabindex="0">
    Propagating the Completion of a State-Manipulation Operation</mshelp:link>.

From the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <i>ProtocolTerminateOffloadComplete</i> function, the intermediate driver constructs an 
    <mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link> structure. For more information, see 
    <mshelp:link keywords="netvista.reusing_an_ndis_protocol_offload_block_list_structure" tabindex="0">Reusing an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST Structure</mshelp:link>. When calling the 
    <b>NdisMTerminateOffloadComplete</b> function, the intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this newly constructed NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure.



## -see-also

<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

<mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link>

<mshelp:link keywords="netvista.ndis_protocol_offload_block_list" tabindex="0"><b>
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</b></mshelp:link>

<mshelp:link keywords="netvista.ndismterminateoffloadcomplete" tabindex="0"><b>
   NdisMTerminateOffloadComplete</b></mshelp:link>

<a href="..\ndischimney\nf-ndischimney-ndisterminateoffload.md">NdisTerminateOffload</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TERMINATE_OFFLOAD_COMPLETE_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

