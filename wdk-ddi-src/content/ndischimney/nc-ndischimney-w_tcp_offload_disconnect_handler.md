---
UID: NC:ndischimney.W_TCP_OFFLOAD_DISCONNECT_HANDLER
title: W_TCP_OFFLOAD_DISCONNECT_HANDLER
author: windows-driver-content
description: The MiniportTcpOffloadDisconnect function closes the send half of an offloaded TCP connection.
old-location: netvista\miniporttcpoffloaddisconnect.htm
old-project: netvista
ms.assetid: f8be12a9-c2c0-4a22-8a57-58c8b27ef69e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MiniportTcpOffloadDisconnect, MiniportTcpOffloadDisconnect callback function [Network Drivers Starting with Windows Vista], W_TCP_OFFLOAD_DISCONNECT_HANDLER, ndischimney/MiniportTcpOffloadDisconnect, netvista.miniporttcpoffloaddisconnect, tcp_chim_miniport_func_70f2c816-ff74-4297-9d87-50c983a03f2d.xml
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
-	MiniportTcpOffloadDisconnect
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# W_TCP_OFFLOAD_DISCONNECT_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportTcpOffloadDisconnect</i> function closes the send half of an offloaded TCP connection. In
  addition, if the disconnect to be performed is a graceful disconnect, NDIS can supply application data to 
  <i>MiniportTcpOffloadDisconnect</i> function that the function must transmit before sending a FIN
  segment.


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param MiniportOffloadContext [in]

A pointer to a memory location that contains a PVOID value. This PVOID value references the
     miniport offload context that contains the state object for the TCP connection to be disconnected. The
     offload target supplied this PVOID value when it offloaded the TCP connection state object.


### -param NetBufferList [in]

A pointer to a single 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. Only one 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure is associated with this
     NET_BUFFER_LIST structure.


### -param Flags [in]

As one of the following values, the type of disconnect that the offload target must perform:
     





#### TCP_DISCONNECT_ABORTIVE_CLOSE

The offload target must perform an abortive disconnect by sending an RST segment.



#### TCP_DISCONNECT_GRACEFUL_CLOSE

The offload target must perform a graceful disconnect by sending a FIN segment.


## -returns



The 
     <i>MiniportTcpOffloadDisconnect</i> function always returns NDIS_STATUS_PENDING. The offload target
     completes the disconnect request asynchronously by calling 
     <a href="https://msdn.microsoft.com/e862d9fe-a60c-4397-95ce-62aa1ef17eae">
     NdisTcpOffloadDisconnectComplete</a>.




## -remarks



Depending on the 
    <i>Flags</i> setting, the 
    <i>MiniportTcpOffloadDisconnect</i> function performs an abortive disconnect or a graceful disconnect on
    the specified TCP connection.

<b>Abortive Disconnect</b>

If 
    <i>Flags</i> is set to 
    <b>TCP_DISCONNECT_ABORTIVE_CLOSE</b>, the offload target performs an abortive disconnect by sending an
    RST segment on the specified TCP connection.

<div class="alert"><b>Note</b>  This is the only instance in which an offload target can send an RST
    segment.</div>
<div> </div>
Before calling the 
    <a href="https://msdn.microsoft.com/e862d9fe-a60c-4397-95ce-62aa1ef17eae">
    NdisTcpOffloadDisconnectComplete</a> function to complete the abortive disconnect, the offload target
    must complete all outstanding send requests on the connection with a status value of
    NDIS_STATUS_REQUEST_ABORTED. The offload target writes this status value to the 
    <b>Status</b> member of each NET_BUFFER_LIST structure in the linked list that it passes to the 
    <a href="https://msdn.microsoft.com/1689b6f9-88f3-456f-9a7c-c6b4e76cb336">
    NdisTcpOffloadSendComplete</a> function.

It does not matter whether the offload target terminates the outstanding send requests before or after
    it sends the RST segment.

If there are outstanding receive indications or event indications on the connection, the offload
    target must not wait for these indications to complete before sending an RST segment. The offload target
    must immediately stop processing receive segments on the connection and not acknowledge any receive
    segments, including indicated receive data that have not been consumed by the client application.

When 
    <i>Flags</i> =
    <b>TCP_DISCONNECT_ABORTIVE_CLOSE</b>, the NET_BUFFER structure associated with the NET_BUFFER_LIST structure referenced by the 
    <i>NetBufferList</i> pointer contains no data. That is, the 
    <b>DataLength</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a> structure in the 
    <b>NetBufferHeader</b> of the NET_BUFFER structure is zero.

<b>Graceful Disconnect</b>

If 
    <i>Flags</i> is set to 
    <b>TCP_DISCONNECT_GRACEFUL_CLOSE</b>, the offload target performs a graceful disconnect by sending a FIN
    segment on the specified TCP connection.

If there is no user data to be sent before the FIN segment, the NET_BUFFER structure associated with
    the NET_BUFFER_LIST structure referenced by the 
    <i>NetBufferList</i> pointer contains no data. If there is user data to be sent, the memory descriptor
    lists (MDLs) associated with the NET_BUFFER structure contain the user data to be sent.

The offload target should not wait for an acknowledgment of transmitted user data before sending a FIN
    segment. The offload target can send a separate FIN segment after transmitting the user data, or the
    offload target can set the FIN bit in the TCP header of the last segment of user data that it sends.

From the perspective of the offload target, sending a FIN segment closes the send half of the
    connection. Sending a FIN segment, however, does not close the receive half of the connection. The remote
    host terminates the receive half of the connection by sending either of the following to the offload
    target:

<ul>
<li>
A FIN segment, which requests a graceful disconnect.

</li>
<li>
An RST segment, which requests an abortive disconnect.

</li>
</ul>
After sending a FIN segment, the offload target can receive segments on the connection until the
    remote host initiates a graceful or abortive disconnect or until the local host terminates the offload of
    the connection or initiates an abortive disconnect.

Before the offload target calls 
    <a href="https://msdn.microsoft.com/e862d9fe-a60c-4397-95ce-62aa1ef17eae">
    NdisTcpOffloadDisconnectComplete</a>, it must complete all outstanding send requests on the connection
    in the same order in which they were delivered to the offload target.

<b>Mandatory Response to a Disconnect Request
    </b>

An offload target must not fail a disconnect request unless the specified TCP connection is being
    uploaded or is being aborted (for example, because the remote host sent an RST segment on the
    connection). If an offload target fails a disconnect request, the host stack will not reissue the
    disconnect request later.

<b>Freeing Connection Resources
    </b>

The offload target must not free resources for the connection on which it has issued either an
    abortive or graceful disconnect until the host stack terminates the offload of the connection.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/1b808e3c-2d64-44c9-88d3-0a0311e1dc99">MiniportTerminateOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/49b69282-137d-4bb5-92f5-4d27cedbb6d4">
   NdisAdvanceNetBufferDataStart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>



<a href="https://msdn.microsoft.com/e862d9fe-a60c-4397-95ce-62aa1ef17eae">
   NdisTcpOffloadDisconnectComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564609">NdisTcpOffloadSendComplete</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20W_TCP_OFFLOAD_DISCONNECT_HANDLER callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
