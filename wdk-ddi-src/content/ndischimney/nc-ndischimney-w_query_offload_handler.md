---
UID: NC:ndischimney.W_QUERY_OFFLOAD_HANDLER
title: W_QUERY_OFFLOAD_HANDLER
author: windows-driver-content
description: The MiniportQueryOffload function queries previously offloaded TCP chimney state objects.
old-location: netvista\miniportqueryoffload.htm
old-project: netvista
ms.assetid: a583c4cb-53c1-4eff-bcfe-c962f736b1f8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MiniportQueryOffload, MiniportQueryOffload callback function [Network Drivers Starting with Windows Vista], W_QUERY_OFFLOAD_HANDLER, ndischimney/MiniportQueryOffload, netvista.miniportqueryoffload, tcp_chim_miniport_func_920f9145-1dda-4899-85d7-845dd545a6bc.xml
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndischimney.h
apiname:
-	MiniportQueryOffload
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# W_QUERY_OFFLOAD_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportQueryOffload</i> function queries previously offloaded TCP chimney state objects.


## -prototype


````
W_QUERY_OFFLOAD_HANDLER MiniportQueryOffload;

VOID MiniportQueryOffload(
  _In_    NDIS_HANDLE                       MiniportAdapterContext,
  _Inout_ PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
     NdisMSetMiniportAttributes</a> from its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


### -param OffloadBlockList [in, out]

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state that is being queried.


## -returns



None




## -remarks



The 
    <i>MiniportQueryOffload</i> function can query any TCP chimney state that has been offloaded to the
    offload target.

The 
    <i>MiniportQueryOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the query operation
    asynchronously by calling the 
    <a href="..\ndischimney\nf-ndischimney-ndismqueryoffloadstatecomplete.md">
    NdisMQueryOffloadStateComplete</a> function. The 
    <i>OffloadBlockList</i> pointer points to an 
    <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that can either be a stand-alone structure or the root
    node in an 
    <a href="https://msdn.microsoft.com/c96608bd-5e8f-499b-872a-b6f7f33c9e0c">offload state tree</a>. The state tree is valid
    until the offload target calls the 
    <b>NdisMQueryOffloadStateComplete</b> function.

After returning from the 
    <i>MiniportQueryOffload</i> function, the miniport driver fills in the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570939">offload state structure</a> that is
    associated with each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree pointed to by the 
    <i>OffloadBlockList</i> pointer. To each of these offload state structures, the miniport driver writes the
    current value of each variable in the structure.

Before calling the 
    <b>NdisMQueryOffloadStateComplete</b> function, the offload target must write either of the following
    NDIS_STATUS values to the 
    <b>Status</b> member of each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree:

<ul>
<li>
NDIS_STATUS_SUCCESS
     

The offload target successfully queried the state objects.

</li>
<li>
NDIS_STATUS_FAILURE
     

The query operation did not succeed. The host stack will terminate the state objects that could not
     be queried.

</li>
</ul>



## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ndischimney\nf-ndischimney-ndismqueryoffloadstatecomplete.md">
   NdisMQueryOffloadStateComplete</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20W_QUERY_OFFLOAD_HANDLER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

