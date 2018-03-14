---
UID: NA:netdatapathdescriptor
ms.assetid: f82606e1-0b34-386b-af5c-15204a032cfe
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netdatapathdescriptor.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Netdatapathdescriptor.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NetPacketGetFragmentCount function](nf-netdatapathdescriptor-netpacketgetfragmentcount.md) | The NetPacketGetFragmentCount method obtains the total number of fragments in a net packet. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_DATAPATH_DESCRIPTOR structure](ns-netdatapathdescriptor-_net_datapath_descriptor.md) | The NET_DATAPATH_DESCRIPTOR structure describes a datapath queue's ring buffers. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_NET_DATPATH_RING_BUFFER_INDEX enumeration](ne-netdatapathdescriptor-_net_datpath_ring_buffer_index.md) | The NET_DATAPATH_RING_BUFFER_INDEX enumeration defines indices in a datapath queue's array of ring buffers. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER macro](nf-netdatapathdescriptor-net_datapath_descriptor_get_fragment_ring_buffer.md) | The NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER macro retrieves a datapath queue's fragment ring buffer. |
| [NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER macro](nf-netdatapathdescriptor-net_datapath_descriptor_get_packet_ring_buffer.md) | The NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER macro retrieves a datapath queue's packet ring buffer. |
| [NET_PACKET_GET_FRAGMENT macro](nf-netdatapathdescriptor-net_packet_get_fragment.md) | The NET_PACKET_GET_FRAGMENT macro retrieves a single fragment from a net packet. |
