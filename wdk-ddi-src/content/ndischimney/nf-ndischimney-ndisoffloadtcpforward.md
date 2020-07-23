---
UID: NF:ndischimney.NdisOffloadTcpForward
title: NdisOffloadTcpForward function (ndischimney.h)
description: A protocol driver or an intermediate driver calls the NdisOffloadTcpForward function to forward unacknowledged received TCP segments to an underlying driver or offload target.
old-location: netvista\ndisoffloadtcpforward.htm
tech.root: netvista
ms.assetid: ca4e26c5-5fea-42ab-aee6-3ecf4cce3798
ms.date: 05/02/2018
keywords: ["NdisOffloadTcpForward function"]
ms.keywords: NdisOffloadTcpForward, NdisOffloadTcpForward function [Network Drivers Starting with Windows Vista], ndischimney/NdisOffloadTcpForward, netvista.ndisoffloadtcpforward, tcp_chim_ndis_func_9def62ce-e860-4f98-a609-8e96e6381c66.xml
f1_keywords:
 - "ndischimney/NdisOffloadTcpForward"
 - "NdisOffloadTcpForward"
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
- NdisOffloadTcpForward
targetos: Windows
req.typenames: 
---

# NdisOffloadTcpForward function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or an intermediate driver calls the 
  <b>NdisOffloadTcpForward</b> function to forward unacknowledged received TCP segments to an underlying
  driver or offload target.


## -parameters




### -param NdisOffloadHandle [in]

A handle to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_offload_handle">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
     Referencing Offloaded State Through an Intermediate Driver</a>.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes one 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. Each NET_BUFFER structure
     points to a chain of memory descriptor lists (MDLs). The MDLs associated with a NET_BUFFER structure
     contain one and only one TCP segment that is being forwarded to the offload target. The first byte of
     the first MDL is the first byte of the TCP header. The NET_BUFFER_LIST and associated structures are
     locked so that they remain resident in physical memory. However, they are not mapped into system
     memory.


## -returns



The 
     <b>NdisOffloadTcpForward</b> function always returns NDIS_STATUS_PENDING. The forward operation is always
     completed asynchronously.




## -remarks



In response to a call to its 
    <i>MiniportTcpOffloadForward</i> function, an intermediate driver calls the 
    <b>NdisOffloadTcpForward</b> function to propagate the forward operation to the underlying driver or
    offload target. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/propagating-i-o-operations">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcpForward</b> function, the intermediate driver passes the following:

<ul>
<li>
An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

</li>
<li>
The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_forward_handler">
      MiniportTcpOffloadForward</a> function.

</li>
</ul>
When the underlying driver or offload target subsequently completes the forward operation by calling
    the 
    <b>NdisTcpOffloadForwardComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadForwardComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadForwardComplete</b> function to propagate the completion of the forward operation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_forward_handler">MiniportTcpOffloadForward</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_offload_handle">NDIS_OFFLOAD_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_forward_complete">
   NdisTcpOffloadForwardComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-tcp_offload_forward_complete_handler">
   ProtocolTcpOffloadForwardComplete</a>
 

 

