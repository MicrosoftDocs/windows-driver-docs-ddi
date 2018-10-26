---
UID: NC:ndischimney.W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER
title: W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER
author: windows-driver-content
description: NDIS calls the MiniportTcpOffloadReceiveReturn function to return ownership of NET_BUFFER_LIST and associated structures to an offload target.
old-location: netvista\miniporttcpoffloadreceivereturn.htm
tech.root: netvista
ms.assetid: b746f58d-d029-4fcd-a59d-baba037fc38e
ms.date: 05/02/2018
ms.keywords: MiniportTcpOffloadReceiveReturn, MiniportTcpOffloadReceiveReturn callback function [Network Drivers Starting with Windows Vista], W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER, W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER callback, ndischimney/MiniportTcpOffloadReceiveReturn, netvista.miniporttcpoffloadreceivereturn, tcp_chim_miniport_func_c6477511-6f31-4a37-9b28-d157e1fa09af.xml
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
-	MiniportTcpOffloadReceiveReturn
product:
- Windows
targetos: Windows
req.typenames: 
---

# W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls the 
  <i>MiniportTcpOffloadReceiveReturn</i> function to return ownership of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> and associated structures to
  an offload target.


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The miniport driver provided this handle to NDIS when it
     called 
     <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     The linked list can contain NET_BUFFER_LIST structures from one or more calls to the 
     <a href="https://msdn.microsoft.com/a45dede9-6559-4207-a49f-d9627054433a">
     NdisTcpOffloadReceiveHandler</a> function.


## -returns



The 
     <i>MiniportTcpOffloadReceiveReturn</i> function should always succeed. Therefore, the 
     <i>MiniportTcpOffloadReceiveReturn</i> function should always return NDIS_STATUS_SUCCESS.




## -remarks



NDIS calls the 
    <i>MiniportTcpOffloadReceiveReturn</i> function to return ownership of NET_BUFFER_LIST structures and
    associated structures that the offload target passed in one or more previous calls to the 
    <a href="https://msdn.microsoft.com/a45dede9-6559-4207-a49f-d9627054433a">
    NdisTcpOffloadReceiveHandler</a> function.

The 
    <i>MiniportTcpOffloadReceiveReturn</i> function can prepare a returned NET_BUFFER_LIST structure for use
    in a subsequent receive indication. Although the 
    <i>MiniportTcpOffloadReceiveReturn</i> function can return the NET_BUFFER_LIST structures to a pool (for
    example, it could call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562583">NdisFreeNetBufferList</a> function), it
    can be more efficient to reuse the structures without returning them to the pool.

Note that the offload target driver should not unload and the offload target adapter must not be
    closed until all indicated receive buffers have been returned.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562583">NdisFreeNetBufferList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564606">NdisTcpOffloadReceiveHandler</a>
 

 

