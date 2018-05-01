---
UID: NC:ndischimney.NDIS_TCP_OFFLOAD_EVENT_INDICATE
title: NDIS_TCP_OFFLOAD_EVENT_INDICATE
author: windows-driver-content
description: An offload target calls the NdisTcpOffloadEventHandler function to indicate an event that pertains to an offloaded TCP connection.
old-location: netvista\ndistcpoffloadeventhandler.htm
old-project: netvista
ms.assetid: b62e8a07-fe7b-4c52-8795-19e4bb889b6e
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDIS_TCP_OFFLOAD_EVENT_INDICATE, NDIS_TCP_OFFLOAD_EVENT_INDICATE callback, NdisTcpOffloadEventHandler, NdisTcpOffloadEventHandler callback function [Network Drivers Starting with Windows Vista], ndischimney/NdisTcpOffloadEventHandler, netvista.ndistcpoffloadeventhandler, tcp_chim_ndis_func_24cca7c4-aa36-4ff3-8896-93bd0b8517af.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndischimney.h
api_name:
-	NdisTcpOffloadEventHandler
product: Windows
targetos: Windows
req.typenames: 
---

# NDIS_TCP_OFFLOAD_EVENT_INDICATE callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadEventHandler</b> function to indicate an event that pertains to an offloaded TCP
  connection.


## -parameters




### -param NdisOffloadHandle [in]

A handle that identifies the offloaded TCP connection on which the indication is being made. When
     the connection was offloaded, this handle was supplied in the 
     <b>NdisOffloadHandle</b> member of the 
     <a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that was associated with the connection state.


### -param EventType [in]

The event being indicated as one of the following <b>TCP_OFFLOAD_EVENT_TYPE</b> values:
     





#### TcpIndicateDisconnect

Indicates that the remote host has initiated a graceful disconnect by sending a FIN segment on
       the connection.



#### TcpIndicateRetrieve

Indicates that the offload target is requesting the host stack to terminate the offload of a TCP
       connection.



#### TcpIndicateAbort

Indicates that the remote host has initiated an abortive disconnect by sending an acceptable RST
       segment on the connection.



#### TcpIndicateSendBacklogChange

Indicates a change in the preferred send backlog size.


### -param EventSpecificInformation [in]

Specifies additional information about the event being indicated as follows:
     





#### TcpIndicateDisconnect

Not meaningful.



#### TcpIndicateRetrieve

Indicates the reason for the upload request as a <b>TCP_UPLOAD_REASON</b> value. See the Remarks
       section for more information.



#### TcpIndicateAbort

Not meaningful.



#### TcpIndicateSendBacklogChange

Specifies the optimum number of send data bytes that the host stack should have outstanding at
       the offload target.


## -returns



None




## -remarks



<h3><a id="Indicating_a_Graceful_Disconnect"></a><a id="indicating_a_graceful_disconnect"></a><a id="INDICATING_A_GRACEFUL_DISCONNECT"></a>Indicating a Graceful Disconnect</h3>
An offload target should indicate a graceful disconnect only when:

<ul>
<li>
It has received a FIN segment from the remote host.

</li>
<li>
All data received on the connection prior to the reception of the FIN segment has been consumed by
      the client application (that is, there is no receive data to be indicated on the connection).

</li>
</ul>
The offload target must not free the resources for the connection until the host stack terminates the
    offload of the connection.

Note that a graceful disconnect shuts down only the receive half of the connection. It does not shut
    down the send half of the connection.

<h3><a id="Indicating_an_Abortive_Disconnect"></a><a id="indicating_an_abortive_disconnect"></a><a id="INDICATING_AN_ABORTIVE_DISCONNECT"></a>Indicating an Abortive Disconnect</h3>
When an offload target receives an acceptable RST segment on a TCP connection, it must:

<ol>
<li>
In its internal state for the connection, mark the connection as aborted.

</li>
<li>
Call the 
      <b>NdisTcpOffloadEventHandler</b> function with an 
      <i>EventType</i> of 
      <b>TcpIndicateAbort</b>.<div class="alert"><b>Note</b>  When the miniport indicates the <b>TcpIndicateAbort</b> event, the host TCP/IP stack will terminate the offload of the connection. The offload target is free to indicate the <b>TcpIndicateAbort</b> event as soon as the RST segment arrives.</div>
<div> </div>


</li>
<li>
Complete all outstanding send requests and disconnect requests on the connection with
      NDIS_STATUS_REQUEST_ABORTED. The offload target writes this status value to the 
      <b>Status</b> member of each <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure in the linked list that it passes to the 
      <a href="https://msdn.microsoft.com/1689b6f9-88f3-456f-9a7c-c6b4e76cb336">
      NdisTcpOffloadSendComplete</a> function or to the 
      <a href="https://msdn.microsoft.com/e862d9fe-a60c-4397-95ce-62aa1ef17eae">
      NdisTcpOffloadDisconnectComplete</a> function.

</li>
</ol>
The offload target must not free the resources for the connection until the host stack terminates the
    offload of the connection.

<h3><a id="Requesting_Termination_of_a_TCP_Connection"></a><a id="requesting_termination_of_a_tcp_connection"></a><a id="REQUESTING_TERMINATION_OF_A_TCP_CONNECTION"></a>Requesting Termination of a TCP Connection</h3>
The offload target specifies the reason for the termination request as a <b>TCP_UPLOAD_REASON</b> value in
    the 
    <i>EventSpecificInformation</i> parameter that it passes to the 
    <b>NdisTcpOffloadEventHandler</b> function. In response, the host stack calls the 
    <a href="https://msdn.microsoft.com/1b808e3c-2d64-44c9-88d3-0a0311e1dc99">MiniportTerminateOffload</a> function
    of the offload target.

The offload target can request the termination of only one TCP connection per call to 
    <b>NdisTcpOffloadEventHandler</b>. The offload target cannot request the termination of a neighbor state
    object or a path state object. Only the host stack can initiate the termination of a neighbor or path
    state object.

The following table describes events or circumstances that can cause an offload target to request the
    termination of the offload of a TCP connection.

The right-most column indicates, for each <b>TCP_UPLOAD_REASON</b>, whether the host stack always uploads the
    connection (mandatory) or might or might not upload the connection (optional). In the mandatory cases, an
    offload target does not continue processing the offloaded connection. In the optional cases, an offload
    target must be able to continue processing on the offloaded connection if the host stack does not
    terminate the offload of that connection.

<table>
<tr>
<th>Event/Circumstance</th>
<th>TCP_UPLOAD_REASON</th>
<th>Host stack's termination of the TCP connection</th>
</tr>
<tr>
<td>
The hardware state used to track the connection is corrupt.

</td>
<td>
<b>HardwareFailure</b>

</td>
<td>
Mandatory

</td>
</tr>
<tr>
<td>
Offload target attempted to send data on a TCP connection that depends on an invalidated state
       object.

</td>
<td>
<b>InvalidState</b>

</td>
<td>
Mandatory

</td>
</tr>
<tr>
<td>
Offload target receives a segment with the URG bit set in the TCP header. Note that the offload
       target does not send an ACK to acknowledge the urgent data.

</td>
<td>
<b>ReceivedUrgentData</b>

</td>
<td>
Mandatory

</td>
</tr>
<tr>
<td>
A timeout occurred on the TCP connection.

</td>
<td>
<b>TimeoutExpiration</b>

</td>
<td>
Mandatory

</td>
</tr>
<tr>
<td>
The offload target is requesting an upload for an unspecified reason.

</td>
<td>
<b>UploadRequested</b>

</td>
<td>
Mandatory

</td>
</tr>
<tr>
<td>
The offload target has detected that too many transmit segments are being dropped on the TCP
       connection.

</td>
<td>
<b>HighDropRate</b>

</td>
<td>
Optional

</td>
</tr>
<tr>
<td>
The offload target has detected that too many fragments are being received on the TCP
       connection.

</td>
<td>
<b>HighFragmentation</b>

</td>
<td>
Optional

</td>
</tr>
<tr>
<td>
The offload target has received too many out-of-order segments on the TCP connection.

</td>
<td>
<b>HighOutofOrderPackets</b>

</td>
<td>
Optional

</td>
</tr>
<tr>
<td>
The activity (sends/receives) on the TCP connection is too low.

</td>
<td>
<b>LowActivity</b>

</td>
<td>
Optional

</td>
</tr>
<tr>
<td>
There are no preposted receive buffers for the TCP connection.

</td>
<td>
<b>NoBufferProposting</b>

</td>
<td>
Optional

</td>
</tr>
<tr>
<td>
The received buffers posted for the TCP connection are too small.

</td>
<td>
<b>SmallIO</b>

</td>
<td>
Optional

</td>
</tr>
</table>
 

The offload target must not initiate the termination of a half-closed TCP connection when that
    connection is in one of the following states:

<ul>
<li>
FIN_WAIT1--The local host stack has closed the TCP connection, but the connection might still be
      receiving data from the remote endpoint.

</li>
<li>
FIN_WAIT2--The local host has closed the TCP connection and received an ACK for the FIN segment that
      it sent, but the offloaded connection might still be receiving data from the remote host.

</li>
<li>
CLOSE_WAIT--The local host might still be sending data.

</li>
</ul>
An offload target can request the termination of all TCP connections that have been offloaded to it.
    For more information, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563619">NdisMOffloadEventIndicate</a>.

<h3><a id="Indicating_a_Change_in_the_Send_Backlog_Size"></a><a id="indicating_a_change_in_the_send_backlog_size"></a><a id="INDICATING_A_CHANGE_IN_THE_SEND_BACKLOG_SIZE"></a>Indicating a Change in the Send Backlog Size</h3>
The send backlog size can be a function of the round-trip time (RTT) for the connection, the interface
    bandwidth, and other parameters. The specific variables and algorithm that the offload target uses to
    calculate the send backlog size are implementation-specific. An offload target could, for example, use
    minimum of the bandwidth-delay product and the advertised receive window as the algorithm. Note, however,
    that the send backlog size does not vary according to the number of data bytes that are currently posted
    for transmission on the connection.

The offload target should implement a throttling mechanism to ensure that, if the value for 
    <b>SendBacklogSize</b> changes too frequently or by too small an amount, the offload target does not
    indicate a 
    <b>SendBacklogSize</b> event. This will prevent a storm of event indications from occurring.




## -see-also




<a href="https://msdn.microsoft.com/98b22b7f-8881-4029-9558-d5d94bb7878e">Indicating TCP Chimney-Specific Events</a>



<a href="https://msdn.microsoft.com/f430642b-01bf-4ed7-bfea-e8dd8d5a8208">MiniportInitiateOffload</a>



<a href="https://msdn.microsoft.com/1b808e3c-2d64-44c9-88d3-0a0311e1dc99">MiniportTerminateOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563619">NdisMOffloadEventIndicate</a>



<a href="https://msdn.microsoft.com/e862d9fe-a60c-4397-95ce-62aa1ef17eae">
   NdisTcpOffloadDisconnectComplete</a>



<a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
   NdisTcpOffloadReceiveComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564609">NdisTcpOffloadSendComplete</a>



<a href="https://msdn.microsoft.com/b64c0f9e-aa3d-43c5-bdf5-c40cae3929e3">ProtocolTcpOffloadEvent</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/responding-to-the-reception-of-a-fin-or-rst-segment">Responding to
     the Reception of a FIN or RST Segment</a>
 

 

