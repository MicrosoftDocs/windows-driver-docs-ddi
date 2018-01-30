---
UID: NS:ndischimney._NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS
title: "_NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS"
author: windows-driver-content
description: The NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure provides TCP chimney offload information in the OID_TCP_CONNECTION_OFFLOAD_PARAMETERS OIDs:
old-location: netvista\ndis_tcp_connection_offload_parameters.htm
old-project: netvista
ms.assetid: f8d3f971-2abc-425d-9929-518f093262a7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndischimney/PNDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS, netvista.ndis_tcp_connection_offload_parameters, PNDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS, *PNDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS, NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS, _NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS, tcp_chim_struct_481b5b2a-f226-4306-a2a9-640f711fb75b.xml, PNDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], ndischimney/NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS, NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure [Network Drivers Starting with Windows Vista]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndischimney.h
apiname:
-	NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS, NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS"
---

# _NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure provides TCP chimney offload information in the 
  <mshelp:link keywords="netvista.oid_tcp_connection_offload_parameters" tabindex="0">
  OID_TCP_CONNECTION_OFFLOAD_PARAMETERS</mshelp:link> OIDs:


## -syntax


````
typedef struct _NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS {
  NDIS_OBJECT_HEADER         Header;
  NDIS_OFFLOAD_ENCAPSULATION Encapsulation;
  ULONG                      TicksPerSecond;
  UCHAR                      TcpAckFrequency;
  UCHAR                      TcpDelayedAckTicks;
  UCHAR                      TcpMaximumRetransmissions;
  UCHAR                      TcpDoubtReachabilityRetransmissions;
  ULONG                      TcpSwsPreventionTicks;
  ULONG                      TcpDuplicateAckThreshold;
  ULONG                      TcpPushTicks;
  ULONG                      NceStaleTicks;
#if (NDIS_SUPPORT_NDIS61)
  ULONG                      CongestionAlgorithm  :4;
#endif 
} NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS, *PNDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to 
     <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to 
     <b>NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS_ 1</b>, and the 
     <b>Size</b> member to 
     <code>sizeof(NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS)</code>.


### -field Encapsulation

An 
     <mshelp:link keywords="netvista.ndis_offload_encapsulation" tabindex="0"><b>
     NDIS_OFFLOAD_ENCAPSULATION</b></mshelp:link> structure that contains encapsulation settings for TCP chimney
     offload.


### -field TicksPerSecond

A ULONG value that the TCP/IP driver stack sets to specify how many ticks of the host's clock
     equal one second. The default value is 1000 (that is, 1 tick = 1 millisecond). An offload target must
     support this member.


### -field TcpAckFrequency

A UCHAR value that the TCP/IP driver stack sets to specify the maximum number of segments that the
     offload target can receive before the target sends an ACK. An offload target must support this
     member.


### -field TcpDelayedAckTicks

A UCHAR value that the TCP/IP driver stack sets to specify how many ticks, starting from the
     reception of a segment, that the offload target should wait for additional receive segments before the
     target sends an ACK. An offload target uses this value to initialize its delayed-ACK timer. An offload
     target must support this member.


### -field TcpMaximumRetransmissions

A UCHAR value that the TCP/IP driver stack sets to specify the maximum number of times that the
     offload target should retransmit a segment on a TCP connection. When the retransmit counter for a TCP
     connection exceeds this limit, the offload target can call the 
     <mshelp:link keywords="netvista.ndistcpoffloadeventhandler" tabindex="0"><b>
     NdisTcpOffloadEventHandler</b></mshelp:link> function with an 
     <b>EventType</b> parameter of 
     <b>TcpIndicateRetrieve</b> to request that the TCP/IP driver stack terminate the
     offload of the connection. An offload target must support this member.


### -field TcpDoubtReachabilityRetransmissions

A UCHAR value that the TCP/IP driver stack sets to specify the maximum number of times that the
     offload target should retransmit a segment before the target indicates to the TCP/IP driver stack that
     the reachability of a neighbor is in doubt. For more information about this indication, see 
     <a href="..\ndischimney\nf-ndischimney-ndismoffloadeventindicate.md">NdisMOffloadEventIndicate</a>. An
     offload target should support this member.


### -field TcpSwsPreventionTicks

A ULONG value that the TCP/IP driver stack sets to specify the number of ticks for the offload
     target's silly window syndrome (SWS) send and receive timers. When the SWS send timer times out, the
     offload target sends a partial segment. When the SWS receive timer times out, the offload target sends a
     window update. An offload target should support this member.


### -field TcpDuplicateAckThreshold

A ULONG value that the TCP/IP driver stack sets to specify the number of duplicate acknowledgments
     that the offload target must receive before the target performs a fast retransmission. An offload target
     must support this member.


### -field TcpPushTicks

A ULONG value that the TCP/IP driver stack sets to specify the number of ticks that an offload
     target must wait before the target completes a pre-posted receive buffer. This interval starts
     immediately after the offload target places the first byte in the pre-posted receive buffer. An offload
     target uses this value to initialize its push timer. An offload target must support this member.


### -field NceStaleTicks

A ULONG value that the TCP/IP driver stack sets to indicate the number of ticks of inactivity that
     make a neighbor state object stale. An offload target must support this member.


### -field CongestionAlgorithm

Reserved for future use.
     

If you are an independent hardware vendor (IHV) and you want to implement nondefault congestion
     control algorithms, for example Compound TCP, contact Microsoft at 
     <a href="mailto:offloadt@microsoft.com">External TCP Offload Triage</a>.


## -remarks


In NDIS 6.0 and later versions, the NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure specifies the
    current or requested parameters that a miniport adapter provides for TCP chimney offload.

To specify various offload parameter settings, NDIS and overlying drivers supply an
    NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure when they set the 
    <mshelp:link keywords="netvista.oid_tcp_connection_offload_parameters" tabindex="0">
    OID_TCP_CONNECTION_OFFLOAD_PARAMETERS</mshelp:link> OID.

To obtain the current settings of various offload parameters, NDIS and overlying drivers query
    OID_TCP_CONNECTION_OFFLOAD_PARAMETERS. The miniport driver returns the current settings in the
    NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure.

The 
    <b>Encapsulation</b> member of NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS defines the TCP
    chimney offload encapsulation settings for the miniport adapter. For more information, see the 
    <mshelp:link keywords="netvista.full_tcp_offload" tabindex="0">NDIS 6.0 TCP chimney offload
    documentation</mshelp:link>.



## -see-also

<a href="..\ndis\ns-ndis-_ndis_offload_encapsulation.md">NDIS_OFFLOAD_ENCAPSULATION</a>

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">NdisTcpOffloadEventHandler</a>

<mshelp:link keywords="netvista.oid_tcp_connection_offload_parameters" tabindex="0">
   OID_TCP_CONNECTION_OFFLOAD_PARAMETERS</mshelp:link>

<a href="..\ndischimney\nf-ndischimney-ndismoffloadeventindicate.md">NdisMOffloadEventIndicate</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/full-tcp-offload">Full TCP Offload</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

