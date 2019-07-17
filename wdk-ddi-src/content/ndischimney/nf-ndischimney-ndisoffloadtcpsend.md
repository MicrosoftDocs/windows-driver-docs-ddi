---
UID: NF:ndischimney.NdisOffloadTcpSend
title: NdisOffloadTcpSend function (ndischimney.h)
description: A protocol driver or intermediate driver calls the NdisOffloadTcpSend function to transmit data on an offloaded TCP connection.
old-location: netvista\ndisoffloadtcpsend.htm
tech.root: netvista
ms.assetid: a2743bbb-a6fa-4b7e-8087-132e221a5624
ms.date: 05/02/2018
ms.keywords: NdisOffloadTcpSend, NdisOffloadTcpSend function [Network Drivers Starting with Windows Vista], ndischimney/NdisOffloadTcpSend, netvista.ndisoffloadtcpsend, tcp_chim_ndis_func_51f71d27-0877-4046-b80d-8c05765d8e69.xml
ms.topic: function
f1_keywords:
 - "ndischimney/NdisOffloadTcpSend"
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
req.lib: Ndis.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisOffloadTcpSend
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisOffloadTcpSend function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or intermediate driver calls the 
  <b>NdisOffloadTcpSend</b> function to transmit data on an offloaded TCP connection.


## -parameters




### -param NdisOffloadHandle [in]

A handle to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_offload_handle">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
     Referencing Offloaded State Through an Intermediate Driver</a>.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes a list of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures. Each NET_BUFFER structure
     in the list points to a chain of memory descriptor lists (MDLs). The MDLs contain the data to be
     transmitted. The NET_BUFFER_LIST and associated structures are locked so that they remain resident in
     physical memory. However, they are not mapped into system memory.


## -returns



The 
     <b>NdisOffloadTcpSend</b> function always returns NDIS_STATUS_PENDING. The send operation is always
     completed asynchronously.




## -remarks



In response to a call to its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_tcp_offload_send_handler">MiniportTcpOffloadSend</a> function,
    an intermediate driver calls the 
    <b>NdisOffloadTcpSend</b> function to propagate the send operation to the underlying intermediate driver
    or offload target. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/propagating-i-o-operations">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcpSend</b> function, the intermediate driver passes the following:

<ul>
<li>
An 
      <i>NdisOffloadHandle</i> that references the NDIS_OFFLOAD_HANDLE structure stored in the intermediate
      driver's context for the offloaded TCP connection. For more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

</li>
<li>
The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadSend</i> function.

</li>
</ul>
When the underlying driver or offload target subsequently completes the send operation by calling the 
    <b>NdisTcpOffloadSendComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadSendComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadSendComplete</b> function to propagate the completion of the send operation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_tcp_offload_send_handler">MiniportTcpOffloadSend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_offload_handle">NDIS_OFFLOAD_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-ndis_tcp_offload_send_complete">NdisTcpOffloadSendComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-tcp_offload_send_complete_handler">
   ProtocolTcpOffloadSendComplete</a>
 

 

