---
UID: NS:ntddndis._NDIS_TCP_IP_CHECKSUM_OFFLOAD
title: "_NDIS_TCP_IP_CHECKSUM_OFFLOAD"
author: windows-driver-content
description: The NDIS_TCP_IP_CHECKSUM_OFFLOAD structure provides checksum task offload information in the NDIS_OFFLOAD structure.
old-location: netvista\ndis_tcp_ip_checksum_offload.htm
old-project: netvista
ms.assetid: bf5369c5-8656-41a4-a23f-79e40a60d111
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_tcp_ip_checksum_offload, ntddndis/NDIS_TCP_IP_CHECKSUM_OFFLOAD, *PNDIS_TCP_IP_CHECKSUM_OFFLOAD, NDIS_TCP_IP_CHECKSUM_OFFLOAD, tcpip_offload_ref_0214ebce-2667-42c6-8be6-6086d358d2ab.xml, ntddndis/PNDIS_TCP_IP_CHECKSUM_OFFLOAD, PNDIS_TCP_IP_CHECKSUM_OFFLOAD, PNDIS_TCP_IP_CHECKSUM_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], NDIS_TCP_IP_CHECKSUM_OFFLOAD structure [Network Drivers Starting with Windows Vista], _NDIS_TCP_IP_CHECKSUM_OFFLOAD
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
-	NDIS_TCP_IP_CHECKSUM_OFFLOAD
product: Windows
targetos: Windows
req.typenames: "*PNDIS_TCP_IP_CHECKSUM_OFFLOAD, NDIS_TCP_IP_CHECKSUM_OFFLOAD"
---

# _NDIS_TCP_IP_CHECKSUM_OFFLOAD structure


## -description


The NDIS_TCP_IP_CHECKSUM_OFFLOAD structure provides checksum task offload information in the 
  <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure.


## -syntax


````
typedef struct _NDIS_TCP_IP_CHECKSUM_OFFLOAD {
  struct {
    ULONG Encapsulation;
    ULONG IpOptionsSupported  :2;
    ULONG TcpOptionsSupported  :2;
    ULONG TcpChecksum  :2;
    ULONG UdpChecksum  :2;
    ULONG IpChecksum  :2;
  } IPv4Transmit;
  struct {
    ULONG Encapsulation;
    ULONG IpOptionsSupported  :2;
    ULONG TcpOptionsSupported  :2;
    ULONG TcpChecksum  :2;
    ULONG UdpChecksum  :2;
    ULONG IpChecksum  :2;
  } IPv4Receive;
  struct {
    ULONG Encapsulation;
    ULONG IpExtensionHeadersSupported  :2;
    ULONG TcpOptionsSupported  :2;
    ULONG TcpChecksum  :2;
    ULONG UdpChecksum  :2;
  } IPv6Transmit;
  struct {
    ULONG Encapsulation;
    ULONG IpExtensionHeadersSupported  :2;
    ULONG TcpOptionsSupported  :2;
    ULONG TcpChecksum  :2;
    ULONG UdpChecksum  :2;
  } IPv6Receive;
} NDIS_TCP_IP_CHECKSUM_OFFLOAD, *PNDIS_TCP_IP_CHECKSUM_OFFLOAD;
````


## -struct-fields




### -field IPv4Transmit

A structure within NDIS_TCP_IP_CHECKSUM_OFFLOAD that specifies IPv4 transmit information and that
     contains the following members:
     
      


### -field IPv4Transmit.Encapsulation

Encapsulation settings for IPv4 transmit. For more information about this member, see the
       following Remarks section.


### -field IPv4Transmit.IpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate an
       IP checksum for an IPv4 send packet that contains IP options or to indicate that this capability is
       enabled or disabled.


### -field IPv4Transmit.TcpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv4 send packet that contains TCP options or to indicate that this capability is
       enabled or disabled.


### -field IPv4Transmit.TcpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv4 send packet. The TCP/IP transport sets this value to enable this capability
       or to indicate that this capability is enabled or disabled.


### -field IPv4Transmit.UdpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       UDP checksum for an IPv4 send packet or to indicate that this capability is enabled or
       disabled.


### -field IPv4Transmit.IpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate an
       IP checksum for an IPv4 send packet or to indicate that this capability is enabled or disabled.


### -field IPv4Receive

A structure within NDIS_TCP_IP_CHECKSUM_OFFLOAD that specifies IPv4 receive information and that
     contains the following members:
     


### -field IPv4Receive.Encapsulation

Encapsulation settings for IPv4 receive. For more information about this member, see the
       following Remarks section.


### -field IPv4Receive.IpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate an IP
       checksum for an IPv4 receive packet that contains IP options or to indicate that this capability is
       enabled or disabled.


### -field IPv4Receive.TcpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv4 receive packet that contains TCP options or to indicate that this capability
       is enabled or disabled.


### -field IPv4Receive.TcpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate the
       TCP checksum for an IPv4 receive packet or to indicate that this capability is enabled or
       disabled.


### -field IPv4Receive.UdpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate an
       IPv4 receive packet's UDP checksum or to indicate that this capability is enabled or disabled.


### -field IPv4Receive.IpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate an IP
       checksum for an IPv4 receive packet or to indicate that this capability is enabled or disabled.


### -field IPv6Transmit

A structure within NDIS_TCP_IP_CHECKSUM_OFFLOAD that specifies IPv6 transmit information and that
     contains the following members:
     


### -field IPv6Transmit.Encapsulation

Encapsulation settings for IPv6 transmit. For more information about this member, see the
       following Remarks section.


### -field IPv6Transmit.IpExtensionHeadersSupported

A ULONG value that a miniport driver sets to indicate that the miniport adapter can calculate
       checksums on IPv6 packets that contain extension headers.


### -field IPv6Transmit.TcpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv6 send packet that contains TCP options or to indicate that this capability is
       enabled or disabled.


### -field IPv6Transmit.TcpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       TCP checksum for an IPv6 send packet or to indicate that this capability is enabled or
       disabled.


### -field IPv6Transmit.UdpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       UDP checksum for an IPv6 send packet or to indicate that this capability is enabled or
       disabled.


### -field IPv6Receive

A structure within NDIS_TCP_IP_CHECKSUM_OFFLOAD that specifies IPv6 receive information and that
     contains the following members:
     


### -field IPv6Receive.Encapsulation

Encapsulation settings for IPv6 receive. For more information about this member, see the
       following Remarks section.


### -field IPv6Receive.IpExtensionHeadersSupported

A ULONG value that a miniport driver sets to indicate that the miniport adapter can validate
       checksums on IPv6 packets that contain extension headers.


### -field IPv6Receive.TcpOptionsSupported

A ULONG value that a miniport driver sets to indicate that a miniport adapter can calculate a
       checksum for an IPv6 receive packet whose TCP header contains TCP options or to indicate that this
       capability is enabled or disabled.


### -field IPv6Receive.TcpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate an
       IPv6 receive packet's TCP checksum or to indicate that this capability is enabled or disabled.


### -field IPv6Receive.UdpChecksum

A ULONG value that a miniport driver sets to indicate that a miniport adapter can validate a UDP
       checksum for an IPv6 receive packet or to indicate that this capability is enabled or disabled.


## -remarks



The NDIS_TCP_IP_CHECKSUM_OFFLOAD structure is used in the 
    <b>Checksum</b> member of the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure. The
    NDIS_TCP_IP_CHECKSUM_OFFLOAD structure specifies the current or supported services that a miniport
    adapter provides for calculating IP, TCP, or UDP checksums (or all of them) for send packets and
    validating such checksums for receive packets.

NDIS_OFFLOAD is used in the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure, 
    <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure, 
    <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">
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

<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567424">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>



<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_IP_CHECKSUM_OFFLOAD structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

