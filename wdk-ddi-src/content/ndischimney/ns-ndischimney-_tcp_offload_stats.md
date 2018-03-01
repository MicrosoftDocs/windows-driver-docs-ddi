---
UID: NS:ndischimney._TCP_OFFLOAD_STATS
title: "_TCP_OFFLOAD_STATS"
author: windows-driver-content
description: The TCP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a query of OID_TCP4_OFFLOAD_STATS or OID_TCP6_OFFLOAD_STATS.
old-location: netvista\tcp_offload_stats.htm
old-project: netvista
ms.assetid: 959bc46a-c574-4130-a83d-22a695d0d891
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PTCP_OFFLOAD_STATS, PTCP_OFFLOAD_STATS, PTCP_OFFLOAD_STATS structure pointer [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_STATS, TCP_OFFLOAD_STATS structure [Network Drivers Starting with Windows Vista], _TCP_OFFLOAD_STATS, ndischimney/PTCP_OFFLOAD_STATS, ndischimney/TCP_OFFLOAD_STATS, netvista.tcp_offload_stats, tcp_chim_struct_62878657-feff-41e4-b540-cbde66c1244e.xml"
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
-	TCP_OFFLOAD_STATS
product: Windows
targetos: Windows
req.typenames: TCP_OFFLOAD_STATS, *PTCP_OFFLOAD_STATS
---

# _TCP_OFFLOAD_STATS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The TCP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a
  query of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569800">OID_TCP4_OFFLOAD_STATS</a> or 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569801">OID_TCP6_OFFLOAD_STATS</a>.


## -syntax


````
typedef struct _TCP_OFFLOAD_STATS {
  ULONG64 InSegments;
  ULONG64 OutSegments;
  ULONG   CurrentlyEstablished;
  ULONG   ResetEstablished;
  ULONG   RetransmittedSegments;
  ULONG   InErrors;
  ULONG   OutResets;
} TCP_OFFLOAD_STATS, *PTCP_OFFLOAD_STATS;
````


## -struct-fields




### -field InSegments

The total number of segments received on offloaded TCP connections, including those received in
     error (
     <b>InErrors</b> ). This count includes segments received on currently established connections. See 
     <i>tcpInSegs</i> in RFC 1156.


### -field OutSegments

The total number of segments sent on offloaded TCP connections, including those on current
     connections but excluding those containing only retransmitted octets. See 
     <i>tcpOutSegs</i> in RFC 1156.


### -field CurrentlyEstablished

The number of TCP connections for which the current state is either ESTABLISHED or CLOSE-WAIT. See
     
     <i>tcpCurrEstab</i> in RFC 1156.


### -field ResetEstablished

The number of times that offloaded TCP connections have made a direct transition to the CLOSED
     state from either the ESTABLISHED state or the CLOSE-WAIT state.


### -field RetransmittedSegments

The total number of segments retransmitted on offloaded TCP connections--that is, the number of
     TCP segments transmitted that contain one or more previously transmitted octets. See 
     <i>tcpRetransSegs</i> in RFC 1156.


### -field InErrors

The number of packets received on offloaded TCP connections that contained one or more
     TCP-specific errors that prevented the offload target from delivering the packets. See 
     <i>ifInErrors</i> in RFC 1156.


### -field OutResets

The number of segments transmitted on offloaded TCP connections with the RST bit set in the TCP
     header.


## -remarks



The statistics in the TCP_OFFLOAD_STATS structure pertain only to offloaded TCP connections. The
    offload target must not include counts for TCP segments on connections that haven't been offloaded. The
    statistics in the TCP_OFFLOAD_STATS structure pertain to a single network interface.

If an offload target has more than one network interface, it must maintain a separate set of TCP
    statistics counters for each network interface. If the offload target supports both IPv4 and IPv6
    connections on a network interface, it must, for that interface, maintain a separate set of TCP
    statistics counters for TCP/IPv4 traffic and a separate set of TCP statistics counters for TCP/IPv6
    traffic.

If an offload target's TCP chimney capabilities are enabled (see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff558995">NDIS_TASK_OFFLOAD</a>) and if at least one
    offloaded path state object has been offloaded to the offload target, the offload target can process a
    received packet that has a corrupted TCP header (but a valid IP header) in one of two ways:

<ul>
<li>
The offload target can indicate the packet through the non-offload interface by calling the 
      <a href="..\ndis\nf-ndis-ndismindicatereceivenetbufferlists.md">
      NdisMIndicateReceiveNetBufferLists</a> function. In this case, the offload target must not increment
      the 
      <b>InErrors</b> counter. This is the recommended approach.

</li>
<li>
Alternatively, the offload target can drop the corrupted packet and increment the 
      <b>InErrors</b> counter.

</li>
</ul>
If the offload target's TCP chimney capabilities are not enabled or if there is not at least one
    offloaded path state object, the offload target must indicate the corrupted packet and must not increment
    the 
    <b>InErrors</b> counter.

The host stack integrates the statistics returned by an offload target with the statistics that the
    host stack maintains for non-offloaded TCP connections.

Note that the host stack supplies a TCP_OFFLOAD_STATS structure when setting OID_TCP4_OFFLOAD_STATS or
    OID_TCP6_OFFLOAD_STATS. In this case, however, the offload target does not have to examine the values in
    the TCP_OFFLOAD_STATS structure. Instead, when OID_TCP4_OFFLOAD_STATS is set, the offload target should
    reset to zero its TCP statistics counters for offloaded TCP connections that convey IPv4 datagrams. When
    OID_TCP6_OFFLOAD_STATS is set, the offload target should reset to zero its TCP statistics counters for
    offloaded TCP connections that convey IPv6 datagrams.

All of the counters that supply the values for the TCP_OFFLOAD_STATS structure wrap (restart from
    zero) when incremented beyond their maximum counts.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569800">OID_TCP4_OFFLOAD_STATS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569801">OID_TCP6_OFFLOAD_STATS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_STATS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

