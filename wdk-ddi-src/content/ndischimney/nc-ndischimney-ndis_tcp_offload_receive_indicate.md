---
UID: NC:ndischimney.NDIS_TCP_OFFLOAD_RECEIVE_INDICATE
title: NDIS_TCP_OFFLOAD_RECEIVE_INDICATE (ndischimney.h)
description: An offload target calls the NdisTcpOffloadReceiveHandler function to indicate that received network data is available for consumption by a client application.
old-location: netvista\ndistcpoffloadreceivehandler.htm
tech.root: netvista
ms.assetid: a45dede9-6559-4207-a49f-d9627054433a
ms.date: 05/02/2018
ms.keywords: NDIS_TCP_OFFLOAD_RECEIVE_INDICATE, NDIS_TCP_OFFLOAD_RECEIVE_INDICATE callback, NdisTcpOffloadReceiveHandler, NdisTcpOffloadReceiveHandler callback function [Network Drivers Starting with Windows Vista], ndischimney/NdisTcpOffloadReceiveHandler, netvista.ndistcpoffloadreceivehandler, tcp_chim_ndis_func_c79b9638-b69d-49de-b33b-95c0136a45f8.xml
ms.topic: callback
f1_keywords:
 - "ndischimney/NdisTcpOffloadReceiveHandler"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndischimney.h
api_name:
- NdisTcpOffloadReceiveHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_TCP_OFFLOAD_RECEIVE_INDICATE callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadReceiveHandler</b> function to indicate that received network data is available for
  consumption by a client application.


## -parameters




### -param NdisOffloadHandle [in]

A handle that identifies the offloaded TCP connection on which the indication is being made. When
     the connection was offloaded, this handle was supplied in the 
     <b>NdisOffloadHandle</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that was associated with the connection state.


### -param NetBufferList [in]

A pointer to a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. Each 
      <b>NET_BUFFER_LIST</b> structure
      describes a list of 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures. Each 
      <b>NET_BUFFER</b> structure in the list maps to a
      chain of 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">memory descriptor lists (MDLs)</a>. The MDLs contain the
      received data. The MDLs are locked so that they remain resident, but they are not mapped into system
      memory.

The 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure
      specified by 
      <i>NetBufferList</i> must be a stand-alone structure and cannot be the first
      structure in a linked list of 
      <b>NET_BUFFER_LIST</b> structures.
      Offload targets can work around this limitation by chaining as many MDLs as necessary to the same 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> in an offload receive
      indication.


### -param Status [in]

The offload target must supply the following status value:
     





#### NDIS_STATUS_SUCCESS

This indicates that the host stack can retain ownership of the NET_BUFFER_LIST structures and
       associated structures until it returns these structures to the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_receive_return_handler">
       MiniportTcpOffloadReceiveReturn</a> function of the offload target.


### -param BytesConsumed [out]

A pointer to a ULONG-typed variable that receives the number of bytes that were consumed by the
     client application.


## -returns



The 
     <b>NdisTcpOffloadReceiveHandler</b> function can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The client application consumed all the indicated receive data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_OFFLOAD_DATA_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The client application rejected all the indicated receive data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_OFFLOAD_DATA_PARTIALLY_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The client application consumed a subset of the indicated receive data. The amount of data, in
       bytes, that was consumed by the client application is returned in the variable specified by the 
       <i>BytesConsumed</i> parameter.

</td>
</tr>
</table>
 




## -remarks



Receive buffers are posted to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_receive_handler">
    MiniportTcpOffloadReceive</a> function of the offload target. If preposted receive requests (buffers
    supplied by the client application) are available for the connection, the offload target should transfer
    the receive data by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_complete">
    NdisTcpOffloadReceiveComplete</a> function. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/delivery-algorithm">Delivery Algorithm</a>.

All receive requests must be completed by the offload target (even if they are zero-byte receive requests).

After an offload target has indicated receive data and that data has been refused, the offload target
    cannot indicate that data again until the host stack posts a receive request:

<ul>
<li>
Normal receive requests

If the host stack posts normal receive requests, the offload target must complete these requests
      before making any receive indications. For more information see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/delivery-algorithm">Delivery Algorithm</a>.

</li>
<li>
Zero-byte receive requests

The host stack can post a zero-byte receive request to enable receive indications by the offload
      target. A zero-byte receive request is one in which the value of the 
      <b>DataLength</b> member (for more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure) is zero. A
      zero-byte receive request does not consume any buffered data.

</li>
</ul>
During initialization, the offload target should allocate two pools of buffers, each of which contains
    NET_BUFFER_LIST structures and NET_BUFFER structures. The offload target uses one pool for making receive
    indications through the TCP chimney when calling the 
    <b>
    NdisTcpOffloadReceiveHandler</b> function. The offload target uses the other pool for making receive
    indications through the nonoffload NDIS interface when calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
    NdisMIndicateReceiveNetBufferLists</a> function.

Each allocated NET_BUFFER_LIST structure must have only one NET_BUFFER structure associated with it.
    The number of such structures to allocate is up to the driver writer. For more information about
    allocating such structures, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/miniport-driver-buffer-management">Miniport Driver Buffer
    Management</a>.

Provided that it is not making a delayed acknowledgment, the offload target should acknowledge
    received data as soon as the offload target has internal buffers into which it can deposit the data. The
    offload target can acknowledge received data before, during, or after calling the 
    <b>NdisTcpOffloadReceiveHandler</b> function.

The offload target always supplies a 
    <i>Status</i> value of NDIS_STATUS_SUCCESS when calling the 
    <b>NdisTcpOffloadReceiveHandler</b> function. This indicates that the host stack can retain ownership of
    the NET_BUFFER_LIST structures and associated structures until it returns these structures to the offload
    target.

<ul>
<li>
If the host stack returns NDIS_STATUS_SUCCESS, indicating that the client application accepted and
      consumed the receive data, the host stack will return the NET_BUFFER_LIST structures to the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_receive_return_handler">
      MiniportTcpOffloadReceiveReturn</a> function of the offload target. The host stack will set the
      variable specified by the 
      <i>BytesConsumed</i> parameter to the number of bytes that were indicated by the offload target.

</li>
<li>
If the host stack returns NDIS_STATUS_NOT_ACCEPTED, indicating that the client application rejected
      the receive data, the offload target resumes ownership of the indicated NET_BUFFER_LIST structures on
      return of the 
      <b>NdisTcpOffloadReceiveHandler</b> function. The offload target must buffer the receive data in
      anticipation that the client application will post receive buffers on the connection. After the client
      application posts receive buffers, the offload target copies the buffered receive data into the posted
      buffers and completes the posted buffers by calling the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_complete">
      NdisTcpOffloadReceiveComplete</a> function. For more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/delivery-algorithm">Delivery Algorithm</a>. The host stack will
      set the variable specified by the 
      <i>BytesConsumed</i> parameter to zero.

</li>
<li>
If the host stack returns NDIS_STATUS_OFFLOAD_DATA_PARTIALLY_ACCEPTED, indicating that the client
      application consumed a subset of the receive data, the offload target resumes ownership of the
      indicated NET_BUFFER_LIST structures when the 
      <b>NdisTcpOffloadReceiveHandler</b> function returns. The host stack will set the variable specified by
      the 
      <i>BytesConsumed</i> parameter to a non-zero value that specifies the amount of data, in bytes, that was
      consumed by the client application. The offload target must buffer the remaining receive data in
      anticipation that the client application will post the receive buffers on the connection.

</li>
</ul>
Note that the offload target never supplies a 
    <i>Status</i> value of NDIS_STATUS_RESOURCES when calling the 
    <b>NdisTcpOffloadReceiveHandler</b> function.

In the 
    <b>RcvIndicationSize</b> member of the TCP_OFFLOAD_STATE_CACHED structure, the host stack can specify the
    optimum number of data bytes that the offload target should supply in a single call to the 
    <b>NdisTcpOffloadReceiveHandler</b> function. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_indicate">Using the Specified
    Receive Indication Size</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_receive_handler">MiniportTcpOffloadReceive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_receive_return_handler">
   MiniportTcpOffloadReceiveReturn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
 

 

