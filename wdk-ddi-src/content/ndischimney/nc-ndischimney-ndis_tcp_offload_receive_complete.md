---
UID: NC:ndischimney.NDIS_TCP_OFFLOAD_RECEIVE_COMPLETE
title: NDIS_TCP_OFFLOAD_RECEIVE_COMPLETE
author: windows-driver-content
description: An offload target calls the NdisTcpOffloadReceiveComplete function to return posted receive requests (receive buffers) to the host stack.
old-location: netvista\ndistcpoffloadreceivecomplete.htm
old-project: netvista
ms.assetid: d5b1341b-cbe0-483c-9abb-b8706f2db2dd
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_TCP_OFFLOAD_RECEIVE_COMPLETE, NdisTcpOffloadReceiveComplete, NdisTcpOffloadReceiveComplete callback function [Network Drivers Starting with Windows Vista], ndischimney/NdisTcpOffloadReceiveComplete, netvista.ndistcpoffloadreceivecomplete, tcp_chim_ndis_func_7d17cfb0-d83a-42e2-9ac8-042bf1964991.xml
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndischimney.h
api_name:
-	NdisTcpOffloadReceiveComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NDIS_TCP_OFFLOAD_RECEIVE_COMPLETE callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadReceiveComplete</b> function to return posted receive requests (receive buffers) to the
  host stack. The offload target previously received the receive requests in one or more calls to its 
  <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">
  MiniportTcpOffloadReceive</a> function.


## -prototype


````
VOID NdisTcpOffloadReceiveComplete(
  _In_ NDIS_HANDLE      NdisMiniportHandle,
  _In_ PNET_BUFFER_LIST NetBufferList
);
````


## -parameters




### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The offload
     target obtained these structures in one or more calls to its 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">
     MiniportTcpOffloadReceive</a> function.


## -returns



None




## -remarks



An offload target should use and return preposted receive requests in the order in which the requests
    were posted to the 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">
    MiniportTcpOffloadReceive</a> function of the offload target. That is, the offload target should use
    and return preposted receive requests in first in, first out (FIFO) order.

An offload target must serialize calls to the 
    <b>NdisTcpOffloadReceiveComplete</b> function and to the 
    <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">
    NdisTcpOffloadReceiveHandler</a> function on a per -connection basis.

An offload target's 
    <i>MiniportTcpOffloadReceive</i> function can be called in the context of an offload target's call to the 
    <b>NdisTcpOffloadReceiveComplete</b> function. In this case, an offload target must not call the 
    <b>NdisTcpOffloadReceiveComplete</b> function again until the previous call to 
    <b>NdisTcpOffloadReceiveComplete</b> has returned.

To improve system performance, an offload target can create a linked list that contains the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures from multiple
    calls to its 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">
    MiniportTcpOffloadReceive</a> function. The offload target can pass such a linked list in a single call
    to the 
    <b>NdisTcpOffloadReceiveComplete</b> function. Note that, an offload target can distribute the receive
    requests that were posted in a single call to the 
    <i>
    MiniportTcpOffloadReceive</i> function across more than one completion call as long the offload target
    completes the receive requests in the same order that they were posted to the 
    <i>MiniportTcpOffloadReceive</i> function.

Before calling the 
    <b>NdisTcpOffloadReceiveComplete</b> function, the offload target does the following for each
    NET_BUFFER_LIST structure that it passes to the function:

<ul>
<li>Writes one of the following status values to the 
     <b>Status</b> member:
     

<dl>
<dt><a id="NDIS_STATUS_SUCCESS"></a><a id="ndis_status_success"></a>NDIS_STATUS_SUCCESS</dt>
<dd>
The offload target received all the data associated with the NET_BUFFER_LIST structures that are
       referenced by the 
       <i>NetBufferList</i> parameter. The offload target also advanced the 
       <i>RcvNxt</i> and 
       <i>RcvWnd</i> variables in the TCP delegated state for the TCP connection. The offload target might or
       might not have generated an acknowledgment for the received data, depending on whether the offload
       target is waiting to send a delayed acknowledgment.

</dd>
<dt><a id="NDIS_STATUS_REQUEST_ABORTED"></a><a id="ndis_status_request_aborted"></a>NDIS_STATUS_REQUEST_ABORTED</dt>
<dd>
An error occurred while the offload target was processing the received data. If the offload
       target is supplying some valid data with the NET_BUFFER_LIST structures that are pointed to by the 
       <i>NetBufferList</i> parameter, the offload target specifies the number of valid data bytes by calling
       the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro. The
       offload target might or might not have acknowledged some portion of the received data.

</dd>
<dt><a id="NDIS_STATUS_UPLOAD_IN_PROGRESS"></a><a id="ndis_status_upload_in_progress"></a>NDIS_STATUS_UPLOAD_IN_PROGRESS</dt>
<dd>
The connection on which the buffer was posted is being uploaded.

</dd>
</dl>


<dl>
<dt><a id="NDIS_STATUS_INVALID_STATE"></a><a id="ndis_status_invalid_state"></a>NDIS_STATUS_INVALID_STATE</dt>
<dd>
The receive request was posted after the offload target indicated a disconnect by calling 
       <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">
       NdisTcpOffloadEventHandler</a>.

</dd>
</dl>
</li>
</ul>
<ul>
<li>
Specifies the number of data bytes returned by calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro with an 
      <i>id</i> of 
      <b>TcpOffloadBytesTransferred</b>.

</li>
<li>
Calls the 
      <a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
      NdisAdvanceNetBufferDataStart</a> function. The 
      <i>NetBufferList</i> parameter should point to the NET_BUFFER structure that is associated with the
      NET_BUFFER_LIST structure. The 
      <i>DataOffsetDelta</i> parameter should specify the number of data bytes that the offload target placed
      in the memory descriptor lists (MDLs) associated with the NET_BUFFER structure. The 
      <i>FreeMdl</i> parameter should be <b>NULL</b>.

</li>
</ul>



## -see-also

<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">MiniportTcpOffloadReceive</a>



<a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
   NdisAdvanceNetBufferDataStart</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_OFFLOAD_RECEIVE_COMPLETE callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

