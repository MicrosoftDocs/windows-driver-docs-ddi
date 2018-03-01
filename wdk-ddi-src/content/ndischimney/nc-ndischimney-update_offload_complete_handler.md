---
UID: NC:ndischimney.UPDATE_OFFLOAD_COMPLETE_HANDLER
title: UPDATE_OFFLOAD_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol driver's or intermediate driver's ProtocolUpdateOffloadComplete function to complete an update offload operation that the driver previously initiated by calling the NdisUpdateOffload function.
old-location: netvista\protocolupdateoffloadcomplete.htm
old-project: netvista
ms.assetid: 3cd7a32a-d560-429b-b191-aeabb87433f3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ProtocolUpdateOffloadComplete, ProtocolUpdateOffloadComplete callback function [Network Drivers Starting with Windows Vista], UPDATE_OFFLOAD_COMPLETE_HANDLER, ndischimney/ProtocolUpdateOffloadComplete, netvista.protocolupdateoffloadcomplete, tcp_chim_protocol_func_dd66a468-9cad-4763-8eea-f7502811368e.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndischimney.h
api_name:
-	ProtocolUpdateOffloadComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# UPDATE_OFFLOAD_COMPLETE_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolUpdateOffloadComplete</i> function to complete an update offload operation that the driver
  previously initiated by calling the 
  <a href="..\ndischimney\nf-ndischimney-ndisupdateoffload.md">NdisUpdateOffload</a> function.


## -prototype


````
UPDATE_OFFLOAD_COMPLETE_HANDLER ProtocolUpdateOffloadComplete;

VOID ProtocolUpdateOffloadComplete(
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
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function


### -param OffloadBlockList [in]

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_protocol_offload_block_list.md">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state that was updated or that was
     attempted to be updated.


## -returns



None




## -remarks



In response to an underlying offload target's or intermediate driver's call to the 
    <a href="..\ndischimney\nf-ndischimney-ndismupdateoffloadcomplete.md">
    NdisMUpdateOffloadComplete</a> function, NDIS calls a protocol or intermediate driver's 
    <i>ProtocolUpdateOffloadComplete</i> function.

An intermediate driver must propagate the completion of the update offload operation to the driver
    above it by calling 
    <b>NdisMUpdateOffloadComplete</b>. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/propagating-the-completion-of-a-state-manipulation-operation">
    Propagating the Completion of a State-Manipulation Operation</a>.

From the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <i>ProtocolUpdateOffloadComplete</i> function, the intermediate driver constructs an 
    <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/reusing-an-ndis-protocol-offload-block-list-structure">Reusing an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST Structure</a>. When calling the 
    <b>NdisMUpdateOffloadComplete</b> function, the intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this newly constructed NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure.




## -see-also

<a href="..\ndischimney\nf-ndischimney-ndisupdateoffload.md">NdisUpdateOffload</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a>



<a href="..\ndischimney\nf-ndischimney-ndismupdateoffloadcomplete.md">NdisMUpdateOffloadComplete</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_protocol_offload_block_list.md">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20UPDATE_OFFLOAD_COMPLETE_HANDLER callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

