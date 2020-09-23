---
UID: NS:ntddndis._NDIS_TCP_LARGE_SEND_OFFLOAD_V2
title: _NDIS_TCP_LARGE_SEND_OFFLOAD_V2 (ntddndis.h)
description: The NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure provides large send offload version 2 (LSOV2) information in the NDIS_OFFLOAD structure.
old-location: netvista\ndis_tcp_large_send_offload_v2.htm
tech.root: netvista
ms.assetid: e53e5771-a3ca-4867-a0ac-65adb66e574c
ms.date: 05/02/2018
keywords: ["NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure"]
ms.keywords: "*PNDIS_TCP_LARGE_SEND_OFFLOAD_V2, NDIS_TCP_LARGE_SEND_OFFLOAD_V2, NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_LARGE_SEND_OFFLOAD_V2, PNDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TCP_LARGE_SEND_OFFLOAD_V2, netvista.ndis_tcp_large_send_offload_v2, ntddndis/NDIS_TCP_LARGE_SEND_OFFLOAD_V2, ntddndis/PNDIS_TCP_LARGE_SEND_OFFLOAD_V2, tcpip_offload_ref_739d5001-8b37-437f-ad2e-8ad817feb59d.xml"
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
req.typenames: NDIS_TCP_LARGE_SEND_OFFLOAD_V2, *PNDIS_TCP_LARGE_SEND_OFFLOAD_V2
f1_keywords:
 - _NDIS_TCP_LARGE_SEND_OFFLOAD_V2
 - ntddndis/_NDIS_TCP_LARGE_SEND_OFFLOAD_V2
 - PNDIS_TCP_LARGE_SEND_OFFLOAD_V2
 - ntddndis/PNDIS_TCP_LARGE_SEND_OFFLOAD_V2
 - NDIS_TCP_LARGE_SEND_OFFLOAD_V2
 - ntddndis/NDIS_TCP_LARGE_SEND_OFFLOAD_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_TCP_LARGE_SEND_OFFLOAD_V2
---

# _NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure


## -description

The <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> structure provides large send offload version 2 (LSOV2)
  information in the 
  <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> structure.

## -struct-fields

### -field IPv4

A structure within <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> that specifies IPv4 information and that
     contains the following members:

### -field IPv4.Encapsulation

Encapsulation settings for IPv4. For more information about this member, see the following
       Remarks section.

### -field IPv4.MaxOffLoadSize

The maximum bytes of user data that the transport can pass to the miniport driver in a single
       packet. The transport will not pass a packet to the miniport driver that contains more user data bytes
       than 
       <b>MaxOffLoadSize</b> specifies. If such a packet must be transmitted, the transport itself segments
       the packet into smaller packets.

### -field IPv4.MinSegmentCount

The minimum number of segments that a large TCP packet must be divisible by before the transport
       can offload it to the hardware for segmentation. The transport will not offload a large packet to the
       miniport driver for segmentation unless the miniport driver can create at least as many segments as 
       <b>MinSegmentCount</b> specifies from the packet. If a large TCP packet does not meet the
       minimum-segment requirement, the TCP/IP transport itself segments the packet into smaller
       packets.

### -field IPv6

A structure within <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> that specifies IPv6 information and that
     contains the following members:

### -field IPv6.Encapsulation

Encapsulation settings for IPv6. For more information about this member, see the following
       Remarks section.

### -field IPv6.MaxOffLoadSize

The maximum bytes of user data that the transport can pass to the miniport driver in a single
       packet. The transport will not pass a packet to the miniport driver that contains more user data bytes
       than 
       <b>MaxOffLoadSize</b> specifies. If such a packet must be transmitted, the transport itself segments
       the packet into smaller packets.

### -field IPv6.MinSegmentCount

The minimum number of segments that a large TCP packet must be divisible by before the transport
       can offload it to a NIC for segmentation. The transport will not offload a large packet to the
       miniport driver for segmentation unless the miniport driver can create at least as many segments as 
       <b>MinSegmentCount</b> specifies from the packet. If a large TCP packet does not meet the
       minimum-segment requirement, the TCP/IP transport itself segments the packet into smaller
       packets.

### -field IPv6.IpExtensionHeadersSupported

A ULONG value that a miniport driver sets to indicate that the miniport adapter can segment a
       large TCP packet whose IP header contains IPv6 extension headers.

### -field IPv6.TcpOptionsSupported

A ULONG value that a miniport driver sets to indicate that the miniport driver can segment a
       large TCP packet whose TCP header contains TCP options or to indicate that this capability is enabled
       or disabled.

## -remarks

The <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> structure is used in the 
    <b>LsoV2</b> member of the 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> structure. The
    <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> structure specifies current or supported services that a miniport adapter
    provides for segmenting large TCP packets into smaller packets. NDIS also provides large send offload
    version 1 (LSOV1), which is an earlier version of LSOV2. For more information about LSOV1, see 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v1">
    NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a>.


<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> is used in the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure, 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure, 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">
    NDIS_FILTER_ATTACH_PARAMETERS</a> structure, 
    <a href="/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID, and the 
    <a href="/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

For 
    <a href="/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>,
    the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> structure specifies the task offload capabilities that a miniport adapter supports. If
    the current offloads capabilities change, a miniport driver reports the new capabilities in an 
    <a href="/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

The 
    <b>Encapsulation</b> members of <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> define the LSOV2 encapsulation settings for
    the miniport adapter.

In response to an 
    <a href="/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> query request, NDIS provides a bitwise OR of the encapsulation
    flags, which indicate the supported encapsulation settings, in each of the 
    <b>Encapsulation</b> members. Miniport drivers must provide Ethernet encapsulation
    (NDIS_ENCAPSULATION_IEEE_802_3). The other types of encapsulation are optional.

For an 
    <a href="/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication, the miniport driver provides a bitwise
    OR of the encapsulation flags, which indicate the current capabilities, in each of the 
    <b>Encapsulation</b> members.

The following flags are defined for the 
    <b>Encapsulation</b> members:

NDIS_ENCAPSULATION_NOT_SUPPORTED  
Specifies that no encapsulation offload is supported.

NDIS_ENCAPSULATION_NULL  
Specifies NULL encapsulation.

NDIS_ENCAPSULATION_IEEE_802_3  
Specifies IEEE 802.3 encapsulation.

NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q  
Specifies IEEE 802.3p and IEEE 802.3q encapsulation.

NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB  
Specifies that IEEE 802.3p and IEEE 802.3q encapsulation settings are specified in the NetBufferListInfo member of each NET_BUFFER_LIST structure.

NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED  
Specifies logical link control (LLC) encapsulation for routed protocols, as described in RFC 1483. This flag is also used to indicate Ethernet LLC/SNAP encapsulation.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v1">
   NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>