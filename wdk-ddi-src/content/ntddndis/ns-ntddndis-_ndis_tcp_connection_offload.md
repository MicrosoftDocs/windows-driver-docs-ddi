---
UID: NS:ntddndis._NDIS_TCP_CONNECTION_OFFLOAD
title: _NDIS_TCP_CONNECTION_OFFLOAD (ntddndis.h)
description: The NDIS_TCP_CONNECTION_OFFLOAD structure provides connection offload information for current settings and for supported capabilities.
old-location: netvista\ndis_tcp_connection_offload.htm
tech.root: netvista
ms.date: 07/26/2019
keywords: ["NDIS_TCP_CONNECTION_OFFLOAD structure"]
ms.keywords: "*PNDIS_TCP_CONNECTION_OFFLOAD, NDIS_TCP_CONNECTION_OFFLOAD, NDIS_TCP_CONNECTION_OFFLOAD structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_CONNECTION_OFFLOAD, PNDIS_TCP_CONNECTION_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TCP_CONNECTION_OFFLOAD, netvista.ndis_tcp_connection_offload, ntddndis/NDIS_TCP_CONNECTION_OFFLOAD, ntddndis/PNDIS_TCP_CONNECTION_OFFLOAD, tcpip_offload_ref_d53e40a7-cf71-4281-ba14-80d913f810d7.xml"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
targetos: Windows
req.typenames: NDIS_TCP_CONNECTION_OFFLOAD, *PNDIS_TCP_CONNECTION_OFFLOAD
f1_keywords:
 - _NDIS_TCP_CONNECTION_OFFLOAD
 - ntddndis/_NDIS_TCP_CONNECTION_OFFLOAD
 - PNDIS_TCP_CONNECTION_OFFLOAD
 - ntddndis/PNDIS_TCP_CONNECTION_OFFLOAD
 - NDIS_TCP_CONNECTION_OFFLOAD
 - ntddndis/NDIS_TCP_CONNECTION_OFFLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_TCP_CONNECTION_OFFLOAD
 - PNDIS_TCP_CONNECTION_OFFLOAD
 - NDIS_TCP_CONNECTION_OFFLOAD
---

# _NDIS_TCP_CONNECTION_OFFLOAD structure


## -description

The NDIS_TCP_CONNECTION_OFFLOAD structure provides connection offload information for current
  settings and for supported capabilities.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_TCP_CONNECTION_OFFLOAD structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to 
     <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to 
     <b>NDIS_TCP_CONNECTION_OFFLOAD_REVISION_1</b>, and the 
     <b>Size</b> member to 
     <b>NDIS_SIZEOF_TCP_CONNECTION_OFFLOAD_REVISION_1</b>.

### -field Encapsulation

Encapsulation settings for TCP chimney offload. For more information about this member, see the following Remarks section.

### -field SupportIPv4

A ULONG value that an offload target sets to indicate that it supports IPv4. The TCP/IP driver
     stack sets this member to enable IPv4.

### -field SupportIPv6

A ULONG value that an offload target sets to indicate that it supports IPv6. The TCP/IP driver
     stack sets this member to enable IPv6. Note that an offload target can support both IPv4 and
     IPv6.

### -field SupportIPv6ExtensionHeaders

A ULONG value that an offload target sets to indicate that it supports IPv6 extension headers
     (that is, routing, fragmentation/reassembly, authentication, encapsulation, hop-by-hop processing, and
     destination options). The TCP/IP driver stack sets this member to enable IPv6 extension headers.

### -field SupportSack

A ULONG value that an offload target sets to indicate that it supports TCP selective
     acknowledgments (SACKs) for both transmit and receive operations. The TCP/IP driver stack sets this
     member to enable SACKs for both transmit and receive operations.
     

If an offload target sets the 
     <b>SupportSack</b> member, the target must be able to generate and consume SACK
     segments. If an offload target does not support the SACK option, the target must be able to ignore the
     SACK option and process the rest of the TCP segment normally.

### -field CongestionAlgorithm

Reserved for future use.
     

If you are an independent hardware vendor (IHV) and you want to implement nondefault congestion
     control algorithms, for example Compound TCP, contact Microsoft at 
     <a href="mailto:offloadt@microsoft.com">External TCP Offload Triage</a>.

### -field TcpConnectionOffloadCapacity

A ULONG value that an offload target sets to indicate the maximum number of offloaded TCP
     connections that it supports. This number includes both IPv4 and IPv6 connections.

### -field Flags

Reserved.

## -remarks

The NDIS_TCP_CONNECTION_OFFLOAD structure specifies the current or supported services that a miniport
    adapter provides for TCP chimney offload.

The NDIS_TCP_CONNECTION_OFFLOAD structure is used in the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure, 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure, 
    <a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-current-config">
    OID_TCP_CONNECTION_OFFLOAD_CURRENT_CONFIG</a> OID, 
    <a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">
    OID_TCP_CONNECTION_OFFLOAD_HARDWARE_CAPABILITIES</a> OID, NDIS_STATUS_OFFLOAD_RESUME status indication,
    and 
    <a href="/windows-hardware/drivers/network/ndis-status-tcp-connection-offload-hardware-capabilities">
    NDIS_STATUS_TCP_CONNECTION_OFFLOAD_HARDWARE_CAPABILITIES</a> status indication. (For information on
    NDIS_STATUS_OFFLOAD_RESUME, see 
    <a href="/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
    documentation</a>.)

Miniport drivers do not receive the OID queries. NDIS uses the information that the miniport driver
    provides in attributes and status indications to provide responses to OID queries and to provide bind
    parameters.

NDIS supplies an NDIS_TCP_CONNECTION_OFFLOAD structure in response to a query of
    OID_TCP_CONNECTION_OFFLOAD_CURRENT_CONFIG or OID_TCP_CONNECTION_OFFLOAD_HARDWARE_CAPABILITIES. In
    response to an OID_TCP_CONNECTION_OFFLOAD_CURRENT_CONFIG query, the NDIS_TCP_CONNECTION_OFFLOAD structure
    specifies the offload target's current configuration settings. In response to an
    OID_TCP_CONNECTION_OFFLOAD_HARDWARE_CAPABILITIES query, the NDIS_TCP_CONNECTION_OFFLOAD structure
    specifies the offload target's hardware capabilities for offloading TCP connections from the TCP/IP
    transport.

The 
    <b>Encapsulation</b> member of NDIS_TCP_CONNECTION_OFFLOAD defines the TCP chimney
    offload encapsulation settings for the miniport adapter.

For an 
    <a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">
    OID_TCP_CONNECTION_OFFLOAD_HARDWARE_CAPABILITIES</a> query request, NDIS provides a single flag that
    indicates the hardware encapsulation capabilities, in the 
    <b>Encapsulation</b> member.

For an 
    <a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-current-config">
    OID_TCP_CONNECTION_OFFLOAD_CURRENT_CONFIG</a> query request, NDIS provides a bitwise OR of the
    encapsulation flags, which indicates the current encapsulation settings.

The following flags are defined for the 
    <b>Encapsulation</b> member:



<div class="alert"><b>Important</b>  A miniport or mux driver that is chimney capable must set the <b>Encapsulation</b> member to NDIS_ENCAPSULATION_IEEE_802_3, NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED, or both. Otherwise, chimney capability will not be recognized.</div>
<div> </div>
<h3><a id="ddk_ndis_tcp_connection_offload_nr"></a><a id="DDK_NDIS_TCP_CONNECTION_OFFLOAD_NR"></a></h3>
<h3><a id="tcp_chimney_offload_queries"></a><a id="TCP_CHIMNEY_OFFLOAD_QUERIES"></a>TCP Chimney Offload Queries</h3>
When an NDIS responds to a query of 
       <a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">
       OID_TCP_CONNECTION_OFFLOAD_HARDWARE_CAPABILITIES</a> or 
       <a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-current-config">
       OID_TCP_CONNECTION_OFFLOAD_CURRENT_CONFIG</a> for an offload target, NDIS provides the 
       <b>SupportIp4</b>, 
       <b>SupportIp6</b>, 
       <b>SupportIp6ExtensionHeaders</b>, and 
       <b>SupportISack</b> members of the NDIS_TCP_CONNECTION_OFFLOAD structure. These
       members can have one of the following values:



An offload target must support either IPv4 or IPv6 (or both). Offload targets can optionally
       support IPv6 extension headers.

An offload target should not support any IPv4 options. The offload target must forward any received
       IP datagrams that contain IPv4 options to the TCP/IP driver stack. The offload target indicates such
       IP datagrams to the TCP/IP driver stack by calling 
       <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
       NdisMIndicateReceiveNetBufferLists</a>. The TCP/IP driver stack processes the IPv4 options and
       returns the datagrams to the offload target's 
       <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_forward_handler">
       MiniportTcpOffloadForward</a> function. (For information on 
       <i>
       MiniportTcpOffloadForward</i>, see 
       <a href="/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
       documentation</a>.)

The offload target must also provide a value for the 
       <b>TcpConnectionOffloadCapacity</b> member of NDIS_TCP_CONNECTION_OFFLOAD. This
       value should be the maximum number of simultaneously offloaded TCP connections that the offload target
       can support.

Note that an offload target cannot directly indicate new offload capabilities. Instead, the offload
       target must request the TCP/IP driver stack to pause and then resume offloads. When the miniport
       adapter is ready to resume offloading TCP connections, it issues an NDIS_STATUS_OFFLOAD_RESUME status
       indication to report the new connection offload capabilities. For more information on
       NDIS_STATUS_OFFLOAD_RESUME, see 
       <a href="/windows-hardware/drivers/network/full-tcp-offload">NDIS 6.0 TCP chimney offload
       documentation</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a>



<a href="/windows-hardware/drivers/network/ndis-status-tcp-connection-offload-hardware-capabilities">
   NDIS_STATUS_TCP_CONNECTION_OFFLOAD_HARDWARE_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-current-config">
   OID_TCP_CONNECTION_OFFLOAD_CURRENT_CONFIG</a>



<a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">
   OID_TCP_CONNECTION_OFFLOAD_HARDWARE_CAPABILITIES</a>

