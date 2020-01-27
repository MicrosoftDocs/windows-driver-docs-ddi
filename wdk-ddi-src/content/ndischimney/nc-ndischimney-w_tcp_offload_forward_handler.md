---
UID: NC:ndischimney.W_TCP_OFFLOAD_FORWARD_HANDLER
title: W_TCP_OFFLOAD_FORWARD_HANDLER (ndischimney.h)
description: NDIS calls the MiniportTcpOffloadForward function to forward unacknowledged received TCP segments to an offload target.
old-location: netvista\miniporttcpoffloadforward.htm
tech.root: netvista
ms.assetid: e5702476-60a3-4bfc-b959-198e98f0f9ba
ms.date: 05/02/2018
ms.keywords: MiniportTcpOffloadForward, MiniportTcpOffloadForward callback function [Network Drivers Starting with Windows Vista], W_TCP_OFFLOAD_FORWARD_HANDLER, W_TCP_OFFLOAD_FORWARD_HANDLER callback, ndischimney/MiniportTcpOffloadForward, netvista.miniporttcpoffloadforward, tcp_chim_miniport_func_18a2b561-13cd-4337-8ff4-fcd3bfc34b3b.xml
f1_keywords:
 - "ndischimney/MiniportTcpOffloadForward"
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
- MiniportTcpOffloadForward
product:
- Windows
targetos: Windows
req.typenames: 
---

# W_TCP_OFFLOAD_FORWARD_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls the 
  <i>MiniportTcpOffloadForward</i> function to forward unacknowledged received TCP segments to an offload
  target.


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The miniport driver provided this handle to NDIS when it
     called 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param MiniportOffloadContext [in]

A pointer to a memory location that contains a PVOID value. This PVOID value references the
     miniport offload context that contains the state object for the TCP connection for which the TCP
     segments are being forwarded. The offload target supplied this PVOID value when it offloaded the TCP
     connection state object.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. This structure
     may be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes one 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. Each NET_BUFFER structure
     maps to a chain of memory descriptor lists (MDLs). The MDLs associated with a NET_BUFFER structure
     contain one and only one TCP segment that is being forwarded to the offload target. The first byte of
     the first MDL is the first byte of the TCP header. The NET_BUFFER_LIST and associated structures are
     locked so that they remain resident in physical memory. However, they are not mapped into system
     memory.


## -returns



NDIS_STATUS_PENDING is the only allowable return value. An offload target always completes a
     forward request asynchronously by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_forward_complete">
     NdisTcpOffloadForwardComplete</a> function.




## -remarks



The host stack forwards one or more TCP segments that it has received but not acknowledged in the
    following situations:

<ul>
<li>
The host stack received the segments on a TCP connection that was being offloaded to the offload
      target. Since the connection was not fully offloaded, the offload target could not process the TCP
      segments at that time.

</li>
<li>
The host stack is in a multihomed system that received the segments on a network interface other
      than the one on which the TCP connection is offloaded.

</li>
<li>
The offload target previously indicated received packets that had IP options set and/or that were
      fragments that needed reassembling. After processing the IP options and/or successfully reassembling
      the packets, the host stack forwards the TCP segments to the offload target.

</li>
</ul>
The host stack never attempts to forward TCP segments for a TCP connection when:

<ul>
<li>
That connection is being offloaded. The host stack always waits for the offload of the connection to
      complete before forwarding any packets for that connection. The host stack forwards TCP segments as
      soon as possible after the offload of the connection has completed. However, there is no time limit for
      forwarding such segments.

</li>
<li>
The offload of that connection is being terminated. In this case, the host stack buffers the data
      until the termination of the offload completes and then processes the segments.

</li>
</ul>
The host stack forwards TCP segments--not IP datagrams--to an offload target. Therefore, the only
    header that the host stack supplies for each segment is the TCP header, including any TCP options that
    are present. This is all the header information that the offload target needs to process the received
    segment.

When forwarding TCP segments, the host stack transfers one TCP segment per NET_BUFFER structure. The
    host stack associates just one NET_BUFFER structure, and therefore one forwarded TCP segment, with each
    NET_BUFFER_LIST structure in the linked list.

The host stack allocates the NET_BUFFER_LIST and associated structures that NDIS passes to the 
    <i>MiniportTcpOffloadForward</i> function. The offload target owns these resources until it passes them to
    the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_forward_complete">
    NdisTcpOffloadForwardComplete</a> function. While it owns these resources, the offload target is free
    to queue them for processing.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_forward_complete">
   NdisTcpOffloadForwardComplete</a>
 

 

