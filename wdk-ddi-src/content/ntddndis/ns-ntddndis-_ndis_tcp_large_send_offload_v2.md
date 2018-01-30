---
UID: NS:ntddndis._NDIS_TCP_LARGE_SEND_OFFLOAD_V2
title: "_NDIS_TCP_LARGE_SEND_OFFLOAD_V2"
author: windows-driver-content
description: The NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure provides large send offload version 2 (LSOV2) information in the NDIS_OFFLOAD structure.
old-location: netvista\ndis_tcp_large_send_offload_v2.htm
old-project: netvista
ms.assetid: e53e5771-a3ca-4867-a0ac-65adb66e574c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_TCP_LARGE_SEND_OFFLOAD_V2, tcpip_offload_ref_739d5001-8b37-437f-ad2e-8ad817feb59d.xml, ntddndis/PNDIS_TCP_LARGE_SEND_OFFLOAD_V2, NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure pointer [Network Drivers Starting with Windows Vista], PNDIS_TCP_LARGE_SEND_OFFLOAD_V2, netvista.ndis_tcp_large_send_offload_v2, _NDIS_TCP_LARGE_SEND_OFFLOAD_V2, ntddndis/NDIS_TCP_LARGE_SEND_OFFLOAD_V2, *PNDIS_TCP_LARGE_SEND_OFFLOAD_V2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddndis.h
apiname:
-	NDIS_TCP_LARGE_SEND_OFFLOAD_V2
product: Windows
targetos: Windows
req.typenames: "*PNDIS_TCP_LARGE_SEND_OFFLOAD_V2, NDIS_TCP_LARGE_SEND_OFFLOAD_V2"
---

# _NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure


## -description


The <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> structure provides large send offload version 2 (LSOV2)
  information in the 
  <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure.


## -syntax


````
typedef struct _NDIS_TCP_LARGE_SEND_OFFLOAD_V2 {
  struct {
    ULONG Encapsulation;
    ULONG MaxOffLoadSize;
    ULONG MinSegmentCount;
  } IPv4;
  struct {
    ULONG Encapsulation;
    ULONG MaxOffLoadSize;
    ULONG MinSegmentCount;
    ULONG IpExtensionHeadersSupported  :2;
    ULONG TcpOptionsSupported  :2;
  } IPv6;
} NDIS_TCP_LARGE_SEND_OFFLOAD_V2, *PNDIS_TCP_LARGE_SEND_OFFLOAD_V2;
````


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
    <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure. The
    <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> structure specifies current or supported services that a miniport adapter
    provides for segmenting large TCP packets into smaller packets. NDIS also provides large send offload
    version 1 (LSOV1), which is an earlier version of LSOV2. For more information about LSOV1, see 
    <mshelp:link keywords="netvista.ndis_tcp_large_send_offload_v1" tabindex="0"><b>
    NDIS_TCP_LARGE_SEND_OFFLOAD_V1</b></mshelp:link>.


<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> is used in the 
    <mshelp:link keywords="netvista.ndis_miniport_adapter_offload_attributes" tabindex="0"><b>
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</b></mshelp:link> structure, 
    <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure, 
    <mshelp:link keywords="netvista.ndis_filter_attach_parameters" tabindex="0"><b>
    NDIS_FILTER_ATTACH_PARAMETERS</b></mshelp:link> structure, 
    <mshelp:link keywords="netvista.oid_tcp_offload_current_config" tabindex="0">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</mshelp:link> OID, and the 
    <mshelp:link keywords="netvista.ndis_status_task_offload_current_config" tabindex="0"><b>
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</b></mshelp:link> status indication.

For 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>,
    the <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure specifies the task offload capabilities that a miniport adapter supports. If
    the current offloads capabilities change, a miniport driver reports the new capabilities in an 
    <mshelp:link keywords="netvista.ndis_status_task_offload_current_config" tabindex="0"><b>
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</b></mshelp:link> status indication.

The 
    <b>Encapsulation</b> members of <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> define the LSOV2 encapsulation settings for
    the miniport adapter.

In response to an 
    <mshelp:link keywords="netvista.oid_tcp_offload_current_config" tabindex="0">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</mshelp:link> query request, NDIS provides a bitwise OR of the encapsulation
    flags, which indicate the supported encapsulation settings, in each of the 
    <b>Encapsulation</b> members. Miniport drivers must provide Ethernet encapsulation
    (NDIS_ENCAPSULATION_IEEE_802_3). The other types of encapsulation are optional.

For an 
    <mshelp:link keywords="netvista.ndis_status_task_offload_current_config" tabindex="0"><b>
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</b></mshelp:link> status indication, the miniport driver provides a bitwise
    OR of the encapsulation flags, which indicate the current capabilities, in each of the 
    <b>Encapsulation</b> members.

The following flags are defined for the 
    <b>Encapsulation</b> members:





## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a>

<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

<mshelp:link keywords="netvista.ndis_status_task_offload_current_config" tabindex="0"><b>
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</b></mshelp:link>

<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>

<mshelp:link keywords="netvista.ndis_miniport_adapter_offload_attributes" tabindex="0"><b>
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</b></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<mshelp:link keywords="netvista.ndis_tcp_large_send_offload_v1" tabindex="0"><b>
   NDIS_TCP_LARGE_SEND_OFFLOAD_V1</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

