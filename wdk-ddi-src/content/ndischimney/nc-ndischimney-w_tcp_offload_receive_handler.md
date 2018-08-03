---
UID: NC:ndischimney.W_TCP_OFFLOAD_RECEIVE_HANDLER
title: W_TCP_OFFLOAD_RECEIVE_HANDLER
author: windows-driver-content
description: NDIS calls the MiniportTcpOffloadReceive function to post receive requests (receive buffers) on an offloaded TCP connection.
old-location: netvista\miniporttcpoffloadreceive.htm
tech.root: netvista
ms.assetid: 9c9c033d-e892-4d8a-8f12-4ca34cdc9ea1
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: MiniportTcpOffloadReceive, MiniportTcpOffloadReceive callback function [Network Drivers Starting with Windows Vista], W_TCP_OFFLOAD_RECEIVE_HANDLER, W_TCP_OFFLOAD_RECEIVE_HANDLER callback, ndischimney/MiniportTcpOffloadReceive, netvista.miniporttcpoffloadreceive, tcp_chim_miniport_func_01f5e6c6-4764-41f3-935a-a08754732ea3.xml
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
-	MiniportTcpOffloadReceive
product:
- Windows
targetos: Windows
req.typenames: 
---

# W_TCP_OFFLOAD_RECEIVE_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls the 
  <i>MiniportTcpOffloadReceive</i> function to post receive requests (receive buffers) on an offloaded TCP
  connection.


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The miniport driver provided this handle to NDIS when it
     called 
     <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param MiniportOffloadContext [in]

A pointer to a memory location that contains a PVOID value. This PVOID value references the
     miniport offload context that contains the state object for the TCP connection on which the receive
     requests are being posted. The offload target supplied this PVOID value when it offloaded the TCP
     connection state object.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes one 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure. The NET_BUFFER structure
     maps to a chain of memory descriptor lists (MDLs). The NET_BUFFER_LIST and associated structures are
     locked so that they remain resident in physical memory. However, they are not mapped into system
     memory.


## -returns



NDIS_STATUS_PENDING is the only return value that is allowed. An offload target always completes
     (returns) posted receive requests asynchronously by calling 
     <a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
     NdisTcpOffloadReceiveComplete</a>.




## -remarks



A client application can post receive requests on an offloaded TCP connection. The offload target uses
    these requests to transfer data received on the connection to the client application. If receive requests
    are posted on a connection, the offload target should always use them to transfer data that is received
    on the connection. For more information, see 
    <a href="https://msdn.microsoft.com/13e80cec-03f5-4498-94ab-ce974a8b9697">Delivery Algorithm</a>.

The offload target queues the posted NET_BUFFER_LIST structures in first in, first out (FIFO) order.
    The offload target uses the 
    <b>MiniportReserved</b> member of each NET_BUFFER_LIST structure to queue the structure.

Each NET_BUFFER_LIST structure passed to the 
    <i>MiniportTcpOffloadReceive</i> function has only one NET_BUFFER structure associated with it.

The offload target should place receive data into the posted receive requests in FIFO order. That is,
    data that was received first should be placed into the first posted receive request, and so on.

The host stack serializes calls to the 
    <i>MiniportTcpOffloadReceive</i> function on a per-connection basis. The host stack will not call the 
    <i>MiniportTcpOffloadReceive</i> function on a connection while a call to the 
    <i>MiniportTcpOffloadReceive</i> function on that connection is in progress. This ensures that receive
    requests are always posted in the correct order to an offload target's 
    <i>MiniportTcpOffloadReceive</i> function.

Note, however, that the host stack can call the 
    <i>MiniportTcpOffloadReceive</i> function on a connection before the offload target has completed one or
    more previous calls to the 
    <i>MiniportTcpOffloadReceive</i> function on that same connection. Note also that the host stack can call
    an offload target's 
    <i>MiniportTcpOffloadReceive</i> function on one connection while one or more calls to the 
    <i>MiniportTcpOffloadReceive</i> function are in progress on another connection.

A posted receive request can optionally be in either of two modes:

<ul>
<li>
Push mode

</li>
<li>
Nonpush mode

</li>
</ul>
Note that an offload target must support both push mode and nonpush mode. .

To determine which mode a buffer is in, an offload target calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro to get the
    value of 
    <b>TcpReceiveNoPush</b>. If the value is <b>TRUE</b>, the receive request is in nonpush mode.

If the receive request is in push mode, the offload target retrieves the value of 
    <b>TcpReceiveBytesTransferred</b> by calling the NET_BUFFER_LIST_INFO macro. If this value is non-zero,
    the offload target immediately starts the 
    <a href="https://msdn.microsoft.com/f06fdc3c-70d3-4445-80a5-747237c07295">push timer</a> for the connection. If this value is
    zero, the offload target starts the push timer for the connection as soon as the offload target places
    the first byte of receive data into the receive request. The offload target always completes filled
    receive requests immediately. The offload target completes a partially filled receive request that is in
    push mode if either of the following occurs:

<ul>
<li>
The push timer expires.

</li>
<li>
The offload target receives a TCP segment on the connection that has the PSH bit set.

</li>
</ul>
If the receive request is in nonpush mode, the offload target does not start a push timer. The offload
    target completes the receive request only when the receive request is filled. The offload target ignores
    the PSH bit in TCP segments that it receives on the connection.

If data is received on an offloaded connection while the push timer is running, the offload target
    must restart the push timer for that connection.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>



<a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
   NdisTcpOffloadReceiveComplete</a>
 

 

