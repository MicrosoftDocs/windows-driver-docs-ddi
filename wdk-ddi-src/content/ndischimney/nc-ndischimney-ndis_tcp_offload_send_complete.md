---
UID: NC:ndischimney.NDIS_TCP_OFFLOAD_SEND_COMPLETE
title: NDIS_TCP_OFFLOAD_SEND_COMPLETE (ndischimney.h)
description: An offload target calls the NdisTcpOffloadSendComplete function to complete one or more send requests that were made to the MiniportTcpOffloadSend function of the offload target.
old-location: netvista\ndistcpoffloadsendcomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_TCP_OFFLOAD_SEND_COMPLETE callback function"]
ms.keywords: NDIS_TCP_OFFLOAD_SEND_COMPLETE, NDIS_TCP_OFFLOAD_SEND_COMPLETE callback, NdisTcpOffloadSendComplete, NdisTcpOffloadSendComplete callback function [Network Drivers Starting with Windows Vista], ndischimney/NdisTcpOffloadSendComplete, netvista.ndistcpoffloadsendcomplete, tcp_chim_ndis_func_8893982f-08b9-4963-8a52-533a8ee94cde.xml
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - NDIS_TCP_OFFLOAD_SEND_COMPLETE
 - ndischimney/NDIS_TCP_OFFLOAD_SEND_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndischimney.h
api_name:
 - NdisTcpOffloadSendComplete
---

# NDIS_TCP_OFFLOAD_SEND_COMPLETE callback function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadSendComplete</b> function to complete one or more send requests that were made to the 
  <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_send_handler">MiniportTcpOffloadSend</a> function of
  the offload target.

## -parameters

### -param NdisMiniportHandle 

[in]
The handle that the offload target obtained in a previous call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function.

### -param NetBufferList 

[in]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     The offload target obtained these structures in one or more calls to its 
     <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_send_handler">
     MiniportTcpOffloadSend</a> function.

## -remarks

To improve system performance, an offload target can create a linked list that contains 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures from multiple
    calls to the 
    <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_send_handler">MiniportTcpOffloadSend</a> function.
    The driver can then pass such a linked list in a single call to the 
    <b>NdisTcpOffloadSendComplete</b> function.

Before completing one or more send requests, the offload target must do the following for each
    NET_BUFFER_LIST structure that it passes to the 
    <b>NdisTcpOffloadSendComplete</b> function:

<ul>
<li>
Write a status value to the 
      <b>Status</b> member:

<ul>
<li>NDIS_STATUS_SUCCESS indicates that all data associated with the NET_BUFFER_LIST was successfully
       sent by the offload target and that the offload target received from the remote host an acknowledgment
       for all the transmitted data. Note that this differs from the non-offload send function, 
       <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">
       MiniportSendNetBufferLists</a>, which does not monitor acknowledgments.</li>
<li>A status value other than NDIS_STATUS_SUCCESS--for example, a status value of
       NDIS_STATUS_REQUEST_ABORTED or NDIS_STATUS_UPLOAD_IN_PROGRESS--indicates that the send data was not
       successfully acknowledged. The offload target might or might not have sent the data. The offload
       target should fail the send operation for all subsequent NET_BUFFER_LIST structures in the linked list
       without sending any more data associated with these structures. The offload target writes a status
       value of NDIS_STATUS_UPLOAD_IN_PROGRESS when the offload of the TCP connection on which the data is to
       be sent is being terminated. In this case, the host stack queues and processes the TCP data. The
       offload target writes a status value of NDIS_STATUS_REQUEST_ABORTED if it has received an RST segment
       on the TCP connection on which the data is to be sent. In this case, the host stack does not process
       the TCP data.</li>
<li>The offload target should complete a partial send for, at most, one NET_BUFFER_LIST structure in
       linked list. The offload target writes a status value other than NDIS_STATUS_SUCCESS--for example, a
       status value of NDIS_STATUS_ABORTED or NDIS_STATUS_UPLOAD_IN_PROGRESS--to such a NET_BUFFER_LIST
       structure.</li>
<li>If an intermediate driver cannot allocate memory to propagate the send operation to an
       underlying offload target, it writes a status value of NDIS_STATUS_REQUEST_UPLOAD to the first
       NET_BUFFER_LIST structure in the linked list and NDIS_STATUS_UPLOAD_REQUESTED to all subsequent
       NET_BUFFER_LIST structures in the linked list. The intermediate driver must not propagate the
       NET_BUFFER_LIST structures to an underlying offload target. The host stack will perform the send
       operation.</li>
</ul>
</li>
</ul>
<ul>
<li>
Specify the number of data bytes sent. The offload target does this by calling the 
      <a href="/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a> macro with an 
      <i>id</i> of 
      <b>TcpOffloadBytesTransferred</b>.

</li>
<li>
Call the 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
      NdisAdvanceNetBufferDataStart</a> function for each NET_BUFFER structure that is associated with the
      NET_BUFFER_LIST structure. The 
      <i>NetBuffer</i> parameter passed to the 
      <b>NdisAdvanceNetBufferDataStart</b> function should point to the NET_BUFFER structure. The 
      <i>DataOffsetDelta</i> parameter should specify the number of data bytes from the NET_BUFFER structure
      that were transmitted by the offload target and that were acknowledged by the remote host. The 
      <i>FreeMdl</i> parameter is <b>NULL</b>.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">MiniportSendNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_send_handler">MiniportTcpOffloadSend</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
   NdisAdvanceNetBufferDataStart</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
