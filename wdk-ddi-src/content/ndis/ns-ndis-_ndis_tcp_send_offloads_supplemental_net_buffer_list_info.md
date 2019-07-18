---
UID: NS:ndis._NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO
title: _NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO (ndis.h)
description: The NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO structure contains additional out-of-band information for encapsulated packets.
old-location: netvista\ndis_tcp_send_offloads_supplemental_net_buffer_list_info.htm
tech.root: netvista
ms.assetid: 6688CF73-7048-4709-A50D-1D5DB17C8538
ms.date: 05/02/2018
ms.keywords: "*PNDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO, NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO, NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO, PNDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO, ndis/NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO, ndis/PNDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO, netvista.ndis_tcp_send_offloads_supplemental_net_buffer_list_info"
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO"
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ndis.h
api_name:
- NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO, *PNDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO
---

# _NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO structure


## -description


The <b>NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO</b> structure contains additional out-of-band information for encapsulated packets. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_encapsulated_packet_task_offload">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a> (NVGRE-TO).


## -struct-fields




### -field EncapsulatedPacketOffsets


### -field EncapsulatedPacketOffsets.IsEncapsulatedPacket

If this member is  <b>TRUE</b>, this NBL represents a packet containing an inner Ethernet frame with a transport IP header. It is <b>FALSE</b> for normal packets. When <b>IsEncapsulatedPacket</b> is <b>TRUE</b>, the existing header offset fields, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_tcp_large_send_offload_net_buffer_list_info">NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</a>.<b>LsoV2Transmit</b>.<b>TcpHeaderOffset</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_tcp_ip_checksum_net_buffer_list_info">NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</a>.<b>Transmit</b>.<b>TcpHeaderOffset</b>, will not have correct values and must not be used by the NIC or driver. Instead, the miniport driver must use the offsets specified in the other members of this structure.


### -field EncapsulatedPacketOffsets.EncapsulatedPacketOffsetsValid

If this member is <b>TRUE</b>, the <b>InnerFrameOffset</b>, <b>TransportIpHeaderRelativeOffset</b>, and <b>TcpHeaderRelativeOffset</b> members
have valid values.


### -field EncapsulatedPacketOffsets.InnerFrameOffset

Offset from the beginning of the packet to the first byte of the inner Ethernet frame.


### -field EncapsulatedPacketOffsets.TransportIpHeaderRelativeOffset

Offset to the first byte of the inner IP header relative to the <b>InnerFrameOffset</b>.


### -field EncapsulatedPacketOffsets.TcpHeaderRelativeOffset

Offset to the first byte of the inner (transport) header relative to the <b>TransportIpHeaderRelativeOffset</b>. This value is always set to the correct offset, even if the inner frame is not a TCP packet.


### -field EncapsulatedPacketOffsets.IsInnerIPv6

Set by the protocol driver to indicate that the inner IP header in the encapsulated packet contains IPv6 addresses.


### -field EncapsulatedPacketOffsets.TcpOptionsPresent

Set by the protocol driver when the inner TCP header contains TCP options. This allows a miniport driver to optimize the case when there are no options to assume the TCP header length to access the payload.


### -field EncapsulatedPacketOffsets.Reserved

Reserved for future use.


### -field Value

Reserved for future use.


## -remarks



The members of <b>NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO</b> are meaningful if and only if <b>TcpIpChecksumNetBufferListInfo</b> or <b>TcpLargeSendNetBufferListInfo</b> is specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ne-ndis-_ndis_net_buffer_list_info">NDIS_NET_BUFFER_LIST_INFO</a> structure.

If the <b>IsEncapsulatedPacket</b> member is <b>TRUE</b> and the <b>TcpIpChecksumNetBufferListInfo</b> out-of-band (OOB) information is valid, this indicates that NVGRE support is required and the NIC must compute the checksum for the tunnel (outer) IP header, the transport (inner) IP header, and the TCP or UDP header if one of them is present. An NVGRE packet will only be offloaded if the packet conforms to miniport-advertised capabilities. For example, a packet containing a UDP header will not be offloaded if the miniport did not advertise UDP Tx checksum offload support in its base capabilities. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/offloading-checksum-tasks">Offloading Checksum Tasks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_encapsulated_packet_task_offload">NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ne-ndis-_ndis_net_buffer_list_info">NDIS_NET_BUFFER_LIST_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_encapsulated_packet_task_offload">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/offloading-checksum-tasks">Offloading Checksum Tasks</a>
 

 

