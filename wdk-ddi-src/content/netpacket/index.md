---
UID: NA:netpacket
ms.assetid: 54dc62c9-5c96-374f-b308-15f7917ebfde
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netpacket.h header



This header is used by NetAdapterCx client drivers. For more information, see
- [Network Adapter WDF Class Extension (Cx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/)

Netpacket.h contains these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NetPacketGetExtension function](nf-netpacket-netpacketgetextension.md) | The NetPacketGetExtension method retrieves information stored in one of a packet's extensions. |
| [NetPacketGetPacketChecksum function](nf-netpacket-netpacketgetpacketchecksum.md) | The NetPacketGetPacketChecksum method retrieves checksum information for a packet. |
| [NetPacketGetPacketLargeSendSegmentation function](nf-netpacket-netpacketgetpacketlargesendsegmentation.md) | The NetPacketGetPacketLargeSendSegmentation method retrieves large send offload (LSO) information for a packet. |
| [NetPacketGetPacketReceiveSegmentCoalescence function](nf-netpacket-netpacketgetpacketreceivesegmentcoalescence.md) | The NetPacketGetPacketReceiveSegmentCoalescence method retrieves receive segment coalescence (RSC) information for a packet. |
| [NetPacketIsIpv4 function](nf-netpacket-netpacketisipv4.md) | The NetPacketIsIpv4 method determines if a NET_PACKET is an IPv4 packet. This method is reserved for system use. Do not call this method from your code. |
| [NetPacketIsIpv6 function](nf-netpacket-netpacketisipv6.md) | The NetPacketIsIpv6 method determines if a NET_PACKET is an IPv6 packet. This method is reserved for system use. Do not call this method from your code. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_PACKET structure](ns-netpacket-_net_packet.md) | Represents a single network packet. |
| [_NET_PACKET_CHECKSUM structure](ns-netpacket-_net_packet_checksum.md) | A NET_PACKET_CHECKSUM structure describes checksum information for a NET_PACKET. |
| [_NET_PACKET_FRAGMENT structure](ns-netpacket-_net_packet_fragment.md) | Represents one contiguous buffer in memory. |
| [_NET_PACKET_LARGE_SEND_SEGMENTATION structure](ns-netpacket-_net_packet_large_send_segmentation.md) | The NET_PACKET_LARGE_SEND_SEGMENTATION structure contains large send offload (LSO) information for a packet. |
| [_NET_PACKET_LAYOUT structure](ns-netpacket-_net_packet_layout.md) | A NET_PACKET_LAYOUT structure describes the start of each protocol header in a NET_PACKET. |
| [_NET_PACKET_RECEIVE_SEGMENT_COALESCENCE structure](ns-netpacket-_net_packet_receive_segment_coalescence.md) | The NET_PACKET_RECEIVE_SEGMENT_COALESCENCE structure contains receive segment coalescence (RSC) information for a packet. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [NET_PACKET_GET_FRAGMENT_VALID macro](nf-netpacket-net_packet_get_fragment_valid.md) | The NET_PACKET_GET_FRAGMENT_VALID macro checks if a NET_PACKET contains at least one valid NET_PACKET_FRAGMENT. |
