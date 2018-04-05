---
UID: NS:ntddndis._NDIS_TCP_IP_CHECKSUM_OFFLOAD
title: "_NDIS_TCP_IP_CHECKSUM_OFFLOAD"
author: windows-driver-content
description: The NDIS_TCP_IP_CHECKSUM_OFFLOAD structure provides checksum task offload information in the NDIS_OFFLOAD structure.
old-location: netvista\ndis_tcp_ip_checksum_offload.htm
old-project: netvista
ms.assetid: bf5369c5-8656-41a4-a23f-79e40a60d111
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_TCP_IP_CHECKSUM_OFFLOAD, NDIS_TCP_IP_CHECKSUM_OFFLOAD, NDIS_TCP_IP_CHECKSUM_OFFLOAD structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_IP_CHECKSUM_OFFLOAD, PNDIS_TCP_IP_CHECKSUM_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TCP_IP_CHECKSUM_OFFLOAD, netvista.ndis_tcp_ip_checksum_offload, ntddndis/NDIS_TCP_IP_CHECKSUM_OFFLOAD, ntddndis/PNDIS_TCP_IP_CHECKSUM_OFFLOAD, tcpip_offload_ref_0214ebce-2667-42c6-8be6-6086d358d2ab.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_TCP_IP_CHECKSUM_OFFLOAD
product:
- Windows
targetos: Windows
req.typenames: NDIS_TCP_IP_CHECKSUM_OFFLOAD, *PNDIS_TCP_IP_CHECKSUM_OFFLOAD
---

# _NDIS_TCP_IP_CHECKSUM_OFFLOAD structure


## -description


The NDIS_TCP_IP_CHECKSUM_OFFLOAD structure provides checksum task offload information in the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a> structure.


## -struct-fields




### -field IPv4Transmit

A structure within NDIS_TCP_IP_CHECKSUM_OFFLOAD that specifies IPv4 transmit information and that
     contains the following members:
     
      



#### Encapsulation

Encapsulation settings for IPv4 transmit. For more information about this member, see the
       following Remarks section.



#### IpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate an
       IP checksum for an IPv4 send packet that contains IP options or to indicate that this capability is
       enabled or disabled.



#### TcpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv4 send packet that contains TCP options or to indicate that this capability is
       enabled or disabled.



#### TcpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv4 send packet. The TCP/IP transport sets this value to enable this capability
       or to indicate that this capability is enabled or disabled.



#### UdpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       UDP checksum for an IPv4 send packet or to indicate that this capability is enabled or
       disabled.



#### IpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate an
       IP checksum for an IPv4 send packet or to indicate that this capability is enabled or disabled.


### -field IPv4Receive

A structure within NDIS_TCP_IP_CHECKSUM_OFFLOAD that specifies IPv4 receive information and that
     contains the following members:
     



#### Encapsulation

Encapsulation settings for IPv4 receive. For more information about this member, see the
       following Remarks section.



#### IpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate an IP
       checksum for an IPv4 receive packet that contains IP options or to indicate that this capability is
       enabled or disabled.



#### TcpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv4 receive packet that contains TCP options or to indicate that this capability
       is enabled or disabled.



#### TcpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate the
       TCP checksum for an IPv4 receive packet or to indicate that this capability is enabled or
       disabled.



#### UdpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate an
       IPv4 receive packet's UDP checksum or to indicate that this capability is enabled or disabled.



#### IpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate an IP
       checksum for an IPv4 receive packet or to indicate that this capability is enabled or disabled.


### -field IPv6Transmit

A structure within NDIS_TCP_IP_CHECKSUM_OFFLOAD that specifies IPv6 transmit information and that
     contains the following members:
     



#### Encapsulation

Encapsulation settings for IPv6 transmit. For more information about this member, see the
       following Remarks section.



#### IpExtensionHeadersSupported

A ULONG value that a miniport driver sets to indicate that the miniport adapter can calculate
       checksums on IPv6 packets that contain extension headers.



#### TcpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv6 send packet that contains TCP options or to indicate that this capability is
       enabled or disabled.



#### TcpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv6 send packet or to indicate that this capability is enabled or
       disabled.



#### UdpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       UDP checksum for an IPv6 send packet or to indicate that this capability is enabled or
       disabled.


### -field IPv6Receive

A structure within NDIS_TCP_IP_CHECKSUM_OFFLOAD that specifies IPv6 receive information and that
     contains the following members:
     



#### Encapsulation

Encapsulation settings for IPv6 receive. For more information about this member, see the
       following Remarks section.



#### IpExtensionHeadersSupported

A ULONG value that a miniport driver sets to indicate that the miniport adapter can validate
       checksums on IPv6 packets that contain extension headers.



#### TcpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       checksum for an IPv6 receive packet whose TCP header contains TCP options or to indicate that this
       capability is enabled or disabled.



#### TcpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate an
       IPv6 receive packet's TCP checksum or to indicate that this capability is enabled or disabled.



#### UdpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate a UDP
       checksum for an IPv6 receive packet or to indicate that this capability is enabled or disabled.


## -remarks



The NDIS_TCP_IP_CHECKSUM_OFFLOAD structure is used in the 
    <b>Checksum</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a> structure. The
    NDIS_TCP_IP_CHECKSUM_OFFLOAD structure specifies the current or supported services that a miniport
    adapter provides for calculating IP, TCP, or UDP checksums (or all of them) for send packets and
    validating such checksums for receive packets.

NDIS_OFFLOAD is used in the 
    <a href="https://msdn.microsoft.com/9ce875fc-ed3f-43e9-bfbc-081f02cb1999">
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure, 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564832">NDIS_BIND_PARAMETERS</a> structure, 
    <a href="https://msdn.microsoft.com/d46a1e62-9d03-4ab9-86f6-81b06c04d0f6">
    NDIS_FILTER_ATTACH_PARAMETERS</a> structure, 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID, and the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567424">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

For 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>,
    the NDIS_OFFLOAD structure specifies the task offload capabilities that a miniport adapter supports. If
    the current offloads capabilities change, a miniport driver reports the new capabilities in an 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567424">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

The 
    <b>Encapsulation</b> members of NDIS_TCP_IP_CHECKSUM_OFFLOAD define the checksum offload encapsulation
    settings for the miniport adapter.

In response to an 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> query request, NDIS provides a bitwise OR of the encapsulation
    flags, which indicate the supported encapsulation settings, in each of the 
    <b>Encapsulation</b> members. Miniport drivers must provide Ethernet encapsulation
    (NDIS_ENCAPSULATION_IEEE_802_3). The other types of encapsulation are optional.

For an 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567424">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication, the miniport driver provides a bitwise
    OR of the encapsulation flags, which indicate the current capabilities, in each of the 
    <b>Encapsulation</b> members.

The following flags are defined for the 
    <b>Encapsulation</b> members:



The meaning of the values in the 
    <b>IpOptionsSupported</b>, 
    <b>TcpOptionsSupported</b>, 
    <b>IpExtensionHeadersSupported</b>, 
    <b>TcpChecksum</b>, 
    <b>UdpChecksum</b>, and 
    <b>IpChecksum</b> members of <b>NDIS_TCP_IP_CHECKSUM_OFFLOAD</b> depends on which OID or status indication
    includes the task offload structure: These members can have one of the following values:






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564832">NDIS_BIND_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565481">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/9ce875fc-ed3f-43e9-bfbc-081f02cb1999">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567424">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>
 

 

