---
UID: NC:ndischimney.W_TCP_OFFLOAD_DISCONNECT_HANDLER
title: W_TCP_OFFLOAD_DISCONNECT_HANDLER (ndischimney.h)
description: The MiniportTcpOffloadDisconnect function closes the send half of an offloaded TCP connection.
old-location: netvista\miniporttcpoffloaddisconnect.htm
tech.root: netvista
ms.assetid: f8be12a9-c2c0-4a22-8a57-58c8b27ef69e
ms.date: 05/02/2018
keywords: ["W_TCP_OFFLOAD_DISCONNECT_HANDLER callback function"]
ms.keywords: MiniportTcpOffloadDisconnect, MiniportTcpOffloadDisconnect callback function [Network Drivers Starting with Windows Vista], W_TCP_OFFLOAD_DISCONNECT_HANDLER, W_TCP_OFFLOAD_DISCONNECT_HANDLER callback, ndischimney/MiniportTcpOffloadDisconnect, netvista.miniporttcpoffloaddisconnect, tcp_chim_miniport_func_70f2c816-ff74-4297-9d87-50c983a03f2d.xml
f1_keywords:
 - "ndischimney/MiniportTcpOffloadDisconnect"
 - "MiniportTcpOffloadDisconnect"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndischimney.h
api_name:
- MiniportTcpOffloadDisconnect
targetos: Windows
req.typenames: 
---

# W_TCP_OFFLOAD_DISCONNECT_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportTcpOffloadDisconnect</i> function closes the send half of an offloaded TCP connection. In
  addition, if the disconnect to be performed is a graceful disconnect, NDIS can supply application data to 
  <i>MiniportTcpOffloadDisconnect</i> function that the function must transmit before sending a FIN
  segment.


## -parameters




### -param MiniportAdapterContext 
[in]
The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param MiniportOffloadContext 
[in]
A pointer to a memory location that contains a PVOID value. This PVOID value references the
     miniport offload context that contains the state object for the TCP connection to be disconnected. The
     offload target supplied this PVOID value when it offloaded the TCP connection state object.


### -param NetBufferList 
[in]
A pointer to a single 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. Only one 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure is associated with this
     NET_BUFFER_LIST structure.


### -param Flags 
[in]
As one of the following values, the type of disconnect that the offload target must perform:
     





#### TCP_DISCONNECT_ABORTIVE_CLOSE

The offload target must perform an abortive disconnect by sending an RST segment.



#### TCP_DISCONNECT_GRACEFUL_CLOSE

The offload target must perform a graceful disconnect by sending a FIN segment.


## -returns



The 
     <i>MiniportTcpOffloadDisconnect</i> function always returns NDIS_STATUS_PENDING. The offload target
     completes the disconnect request asynchronously by calling 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_disconnect_complete">
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_disconnect_complete">
    NdisTcpOffloadDisconnectComplete</a> function to complete the abortive disconnect, the offload target
    must complete all outstanding send requests on the connection with a status value of
    NDIS_STATUS_REQUEST_ABORTED. The offload target writes this status value to the 
    <b>Status</b> member of each NET_BUFFER_LIST structure in the linked list that it passes to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_send_complete">
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_data">NET_BUFFER_DATA</a> structure in the 
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_disconnect_complete">
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_terminate_offload_handler">MiniportTerminateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_data">NET_BUFFER_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
   NdisAdvanceNetBufferDataStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_disconnect_complete">
   NdisTcpOffloadDisconnectComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_send_complete">NdisTcpOffloadSendComplete</a>
 

 

