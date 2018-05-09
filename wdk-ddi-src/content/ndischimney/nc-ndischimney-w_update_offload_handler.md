---
UID: NC:ndischimney.W_UPDATE_OFFLOAD_HANDLER
title: W_UPDATE_OFFLOAD_HANDLER
author: windows-driver-content
description: The MiniportUpdateOffload function updates previously offloaded TCP chimney state objects.
old-location: netvista\miniportupdateoffload.htm
old-project: netvista
ms.assetid: b98b2e21-8b28-4da0-9cc9-6fa8cb6e5be7
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: MiniportUpdateOffload, MiniportUpdateOffload callback function [Network Drivers Starting with Windows Vista], W_UPDATE_OFFLOAD_HANDLER, W_UPDATE_OFFLOAD_HANDLER callback, ndischimney/MiniportUpdateOffload, netvista.miniportupdateoffload, tcp_chim_miniport_func_e6dbcab7-ff44-46c0-ae03-729ea479d13c.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndischimney.h
api_name:
-	MiniportUpdateOffload
product:
- Windows
targetos: Windows
req.typenames: 
---

# W_UPDATE_OFFLOAD_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportUpdateOffload</i> function updates previously offloaded TCP chimney state objects.


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload target-allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state objects that are being updated. Only cached
     variables are updated.


## -returns



None




## -remarks



Only cached variables are updated.

The 
    <i>MiniportUpdateOffload</i> function stores the 
    <i>MiniportAdapterContext</i> handle and the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the update operation
    asynchronously by calling the 
    <a href="https://msdn.microsoft.com/aa2c549c-eb16-4d59-9280-1913c8c0266a">
    NdisMUpdateOffloadComplete</a> function. The 
    <i>OffloadBlockList</i> pointer points to an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that can either be
    a stand-alone structure or the root block list in an 
    <a href="https://msdn.microsoft.com/c96608bd-5e8f-499b-872a-b6f7f33c9e0c">offload state tree</a> that contains multiple
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. Such block lists, as well as any 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570939">offload state structures</a> that are
    associated with them, are valid until the miniport driver calls the 
    <b>
    NdisMUpdateOffloadComplete</b> function.

Before the 
    <i>MiniportUpdateOffload</i> function returns, the offload target uses the offload state tree passed to
    the 
    <i>MiniportUpdateOffload</i> function to update offloaded state:

<ul>
<li>
The offload target copies the variable values from any state structures in the tree to the
      corresponding 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/offload-state-objects">offloaded state objects</a>. Only CACHED
      variables are updated.

</li>
<li>
The tree might indicate that path-to-neighbor links must be updated. For more information, see 
      <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff560463">Linking
      Path State Objects to a New Neighbor State Object</a>. In this case, the offload target must update
      its internal representation of offloaded state to reflect the updated links.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563694">NdisMUpdateOffloadComplete</a>
 

 

