---
UID: NS:ndischimney._IP_OFFLOAD_STATS
title: "_IP_OFFLOAD_STATS"
author: windows-driver-content
description: The IP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a query of OID_IP4_OFFLOAD_STATS or OID_IP6_OFFLOAD_STATS.
old-location: netvista\ip_offload_stats.htm
old-project: netvista
ms.assetid: f40c5734-2546-40c3-a6fb-58f728c3cc5e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PIP_OFFLOAD_STATS, IP_OFFLOAD_STATS, IP_OFFLOAD_STATS structure [Network Drivers Starting with Windows Vista], PIP_OFFLOAD_STATS, PIP_OFFLOAD_STATS structure pointer [Network Drivers Starting with Windows Vista], _IP_OFFLOAD_STATS, ndischimney/IP_OFFLOAD_STATS, ndischimney/PIP_OFFLOAD_STATS, netvista.ip_offload_stats, tcp_chim_struct_292881aa-1c15-4b1a-abd9-927d3b3b8f7b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	IP_OFFLOAD_STATS
product: Windows
targetos: Windows
req.typenames: IP_OFFLOAD_STATS, *PIP_OFFLOAD_STATS
---

# _IP_OFFLOAD_STATS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The IP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a
  query of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569758">OID_IP4_OFFLOAD_STATS</a> or 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569759">OID_IP6_OFFLOAD_STATS</a>.


## -struct-fields




### -field InReceives

The total number of input IP datagrams that have been received from the interface on offloaded TCP
     connections, including IP datagrams received in error. See 
     "ipInReceives" in RFC 2011.


### -field InOctets

The total number of octets (bytes) in input IP datagrams that have been received from the
     interface on offloaded TCP connections. Octets from datagrams counted in 
     <b>InReceives</b> must be counted here. 
     <b>InOctets</b> must include the number of bytes in the IP header and payload.


### -field InDelivers

The number of input IP datagrams that were successfully delivered to offloaded TCP connections.
     See 
     "ipInDelivers" in RFC 2011.


### -field OutRequests

The number of IP datagrams that the offload target supplied to its IP layer in requests for
     transmission on offloaded TCP connections. See 
     "ipOutRequests" in RFC 2011.


### -field OutOctets

The total number of octets (bytes) in IP datagrams that the offload target supplied to its IP
     layer in requests for transmission on offloaded TCP connections. Octets from datagrams counted in 
     <b>OutRequests</b> must be counted here. 
     <b>OutOctets</b> must include the number of bytes in the IP header and payload.


### -field InHeaderErrors

The number of input IP datagrams received on offloaded TCP connections that were discarded because
     of errors in their IP headers. Such errors include bad checksums, version number mismatch, other format
     errors, time-to-live exceeded, and errors discovered in processing IPv6 options if the offload target
     supports such options. (An offload target does not process IPv4 options.) This count does not include
     errors resulting from invalid destination addresses. See 
     "ipInHdrErrors" in RFC 2011.


### -field InTruncatedPackets

The number of input IP datagrams discarded because the datagram frame didn't carry enough data. 
     <b>InTruncatedPackets</b> should only be incremented if the frame contained a valid header but was
     otherwise shorter than required. Frames that are too short to contain a valid header should be counted
     as 
     <b>InHeaderErrors</b> .


### -field InDiscards

The number of input IP datagrams received on offloaded TCP connections that contained nothing to
     prevent their further processing but that were discarded for run-time reasons, such as a lack of
     available memory or other resources. See 
     "ipInDiscards" in RFC 2011.


### -field OutDiscards

The number of output IP datagrams that the offload target supplied to its IP layer for which no
     problem was encountered to prevent their transmission but that were discarded for run-time reasons, such
     as a lack of memory or other resources. See 
     "ipOutDiscards" in RFC 2011.


### -field OutNoRoutes

The number of output IP datagrams that the offload target supplied to its IP layer that were
     discarded because no route (such as an offloaded path state object) could be found to transmit them to
     their destination. See 
     "ipOutNoRoutes" in RFC 2011.


## -remarks



The statistics in the IP_OFFLOAD_STATS structure pertain only to IP datagrams that the offload target
    has processed on offloaded TCP connections. The offload target must not include counts for IP datagrams
    on non-offloaded connections. The statistics pertain to a single network interface.

If an offload target has multiple network interfaces, it must maintain separate IP offload statistics
    for each network interface. If the offload target supports both IPv4 and IPv6 connections for a network
    interface, it must maintain one set of IPv4 offload statistics counters and another set of IPv6 offload
    statistics counters for that network interface.

If an offload target's TCP chimney capabilities are enabled (see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff558995">NDIS_TASK_OFFLOAD</a>) and if at least one
    neighbor state object has been offloaded to the offload target, the offload target can process a received
    packet that has a corrupted IP header in one of two ways:

<ul>
<li>
The offload target can indicate the packet through the non-offload interface by calling the 
      <a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
      NdisMIndicateReceiveNetBufferLists</a> function. In this case, the offload target must not increment
      the InHeaderErrors counter. This is the recommended approach.

</li>
<li>
Alternatively, the offload target can drop the corrupted packet 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff558995">NDIS_TASK_OFFLOAD</a> and increment the
      InHeaderErrors counter.

</li>
</ul>
The host stack integrates the statistics returned by an offload target with the statistics that the
    host stack maintains for non-offloaded TCP connections.

Note that the host stack supplies an IP_OFFLOAD_STATS structure when setting OID_IP4_OFFLOAD_STATS or
    OID_IP6_OFFLOAD_STATS. In either case, however, the offload target does not have to examine the values in
    the IP_OFFLOAD_STATS structure. Instead, when OID_IP4_OFFLOAD_STATS is set, the offload target should
    reset all of its IPv4 statistics counters for offloaded TCP connections. When OID_IP6_OFFLOAD_STATS is
    set, the offload target should reset all of its IPv6 statistics counters for offloaded TCP
    connections.

All of the counters that supply the values for the IP_OFFLOAD_STATS structure wrap (restart from zero)
    when incremented beyond their maximum counts.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558995">NDIS_TASK_OFFLOAD</a>



<a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569758">OID_IP4_OFFLOAD_STATS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569759">OID_IP6_OFFLOAD_STATS</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20IP_OFFLOAD_STATS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
