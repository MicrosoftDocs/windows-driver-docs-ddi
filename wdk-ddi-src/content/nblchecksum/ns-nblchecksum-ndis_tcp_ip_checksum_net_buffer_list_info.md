---
UID: NS:nblchecksum._NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
title: NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO structure specifies information used in offloading checksum tasks from the TCP/IP transport to a NIC.
tech.root: netvista 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndis/nblchecksum.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO, *PNDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nblchecksum.h
api_name:
 - _NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
 - PNDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
 - NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
f1_keywords:
 - _NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
 - nblchecksum/_NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
 - PNDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
 - nblchecksum/PNDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
 - NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
 - nblchecksum/NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
dev_langs:
 - c++
---


# _NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO structure


## -description

The <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure specifies information used in offloading
  checksum tasks from the TCP/IP transport to a NIC. The <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure
  is part of the 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> information (out-of-band data)
  that is associated with a <b>NET_BUFFER_LIST</b> structure.

## -struct-fields

### -field Transmit

A structure that contains the following members:

### -field Transmit.IsIPv4

Set by the TCP/IP transport to indicate that the send packet contains IPv4 addresses.

### -field Transmit.IsIPv6

Set by the TCP/IP transport to indicate that the send packet contains IPv6 addresses.

### -field Transmit.TcpChecksum

Set by the TCP/IP transport to indicate that the NIC should calculate the packet's TCP
       checksum.

### -field Transmit.UdpChecksum

Set by the TCP/IP transport to indicate that the NIC should calculate the packet's UDP
       checksum.

### -field Transmit.IpHeaderChecksum

Set by the TCP/IP transport to indicate that the NIC should calculate the IP checksum for the
       first IP header in the packet. If the packet contains both a tunnel IP header and a transport IP
       header, the NIC should calculate the checksum for both IP headers.

### -field Transmit.Reserved

Reserved for NDIS.

### -field Transmit.TcpHeaderOffset

The offset, in bytes, of the TCP header from the beginning of the packet for TCP packets. Miniport drivers can use <b>TcpHeaderOffset</b> to determine the location of the TCP header so that they do not need to parse the MAC and IP header.

### -field Receive

A structure that contains the following members:

### -field Receive.TcpChecksumFailed

Set by the miniport driver to indicate that the TCP checksum calculated by the NIC did not match
       the checksum in the receive packet's TCP header.

### -field Receive.UdpChecksumFailed

Set by the miniport driver to indicate that the UDP checksum calculated by the NIC did not match
       the checksum in the receive packet's UDP header.

### -field Receive.IpChecksumFailed

Set by the miniport driver to indicate that the IP checksum calculated by the NIC did not match
       the checksum in the receive packet's first IP header. If the receive packet contains both a tunnel IP
       header and a transport IP header, the NIC validates the checksum for both IP headers.

<div class="alert"><b>Note</b>  For encapsulated packets that have both a tunnel (outer) IPv4 header and a transport (inner) IPv4 header, the miniport driver should set this flag if either of the IP header checksum validations failed.</div>
<div> </div>

### -field Receive.TcpChecksumSucceeded

Set by the miniport driver to indicate that the TCP checksum calculated by the NIC matched the
       checksum in the receive packet's TCP header.

### -field Receive.UdpChecksumSucceeded

Set by the miniport driver to indicate that the UDP checksum calculated by the NIC matched the
       checksum in the receive packet's UDP header.

### -field Receive.IpChecksumSucceeded

Set by the miniport driver to indicate that the IP checksum calculated by the NIC matched the
       checksum in the receive packet's first IP header. If the receive packet contains both a tunnel IP
       header and a transport IP header, the NIC validates the checksum for the both IP headers.

<div class="alert"><b>Note</b>  For encapsulated packets that have both a tunnel (outer) IPv4 header and a transport (inner) IPv4 header, the miniport driver should set this flag only if both IP header checksum validations succeeded.</div>
<div> </div>

### -field Receive.Loopback

NDIS uses this bit. The miniport driver must not examine or set this bit; the miniport driver
       should just ignore this bit.

### -field Receive.TcpChecksumValueInvalid

A miniport driver that supports <a href="/windows-hardware/drivers/network/receive-segment-coalescing--rsc-">Receive Segment Coalescing (RSC)</a> sets this flag to indicate that the TCP header checksum was validated by the NIC but the TCP header checksum value in the packet is not valid. For more information, see <a href="/windows-hardware/drivers/network/indicating-coalesced-segments">Indicating Coalesced Segments</a>.

Miniport drivers that do  not support RSC should set this flag to zero.

<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later miniport drivers in Windows 8, Windows Server 2012, and later.</div>
<div> </div>

### -field Receive.IpChecksumValueInvalid

A miniport driver that supports RSC sets this flag to indicate that for an IPv4 packet, the IP header checksum was validated by the NIC but the IP header checksum value in the packet is not valid. For a packet consisting of both a tunnel and a transport IP header, this bit is applicable only to the tunnel IP header. For more information, see <a href="/windows-hardware/drivers/network/indicating-coalesced-segments">Indicating Coalesced Segments</a>.

Miniport drivers that do  not support RSC should set this flag to zero.

<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later miniport drivers in Windows 8, Windows Server 2012, and later.</div>
<div> </div>

### -field Value

A <b>PVOID</b> version of the checksum information. Miniport drivers can use this member to access the
      raw information instead of the specific fields.

## -remarks

The <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure specifies information that is used in
    offloading checksum tasks from the TCP/IP transport to a NIC. The
    <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure is part of the 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> information (out-of-band
    data) that is associated with a <b>NET_BUFFER_LIST</b> structure.

Before the TCP/IP transport passes to the miniport driver a TCP/IP packet on which the miniport driver will perform checksum tasks, the TCP/IP transport updates the <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure that is associated with the <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure. Specifically, the TCP/IP transport sets the <b>IsIPv4</b> or <b>IsIPv6</b> flag to indicate that the send packet is an IPv4 or IPv6 packet. 

yyIf the TCP/IP transport does not set either the <b>IsIPv4</b> or <b>IsIPv6</b> flag, the miniport driver should not perform checksum tasks on the packet. If the TCP/IP transport sets the <b>IsIPv4</b> or <b>IsIPv6</b> flag, it also sets the appropriate flags that are required to indicate which checksums the miniport driver should calculate for the packet. For IPv4, this includes the <b>IpHeaderChecksum</b>, <b>TcpChecksum</b>, or <b>UdpChecksum</b> flags. For IPv6, this includes the <b>TcpChecksum</b> or <b>UdpChecksum</b> flags. In addition, for TCP packets, the TCP/IP transport sets the **TcpHeaderOffset** field when either the **IsIPv4** or **IPv6** flag is set. The transport does not set this field for UDP packets.

Before indicating up a receive TCP/IP packet on which it performs checksum tasks, a miniport driver sets the appropriate Xxx<b>ChecksumFailed</b> or Xxx<b>ChecksumSucceeded</b> flags in the <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure.

<div class="alert"><b>Note</b>  Checksum offload is disabled until the miniport receives <a href="/windows-hardware/drivers/network/oid-offload-encapsulation">OID_OFFLOAD_ENCAPSULATION</a>. After it receives this OID, the miniport is then permitted to start validating the checksums on some received packets. The miniport is not required to validate the checksum on every packet; if both the Xxx<b>ChecksumFailed</b> and Xxx<b>ChecksumSucceeded</b> flags are clear, the OS will fall back to validating the checksum in software.</div>
<div> </div>
To obtain the <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure, a driver should call the 
    <a href="/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a> macro with an 
    <i>_Id</i> of 
    <b>TcpIpChecksumNetBufferListInfo</b>.

## -see-also

<a href="/windows-hardware/drivers/network/indicating-coalesced-segments">Indicating Coalesced Segments</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a>