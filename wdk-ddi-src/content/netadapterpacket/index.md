---
UID: NA:netadapterpacket
ms.assetid: 91183c39-d14c-337e-a0cc-6dab9d322698
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netadapterpacket.h header



This header is used by NetAdapterCx client drivers. For more information, see
- [Network Adapter WDF Class Extension (Cx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/)

Netadapterpacket.h contains these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NET_PACKET_EXTENSION_INIT function](nf-netadapterpacket-net_packet_extension_init.md) | The NET_PACKET_EXTENSION_INIT method initializes a NET_PACKET_EXTENSION structure. |
| [NET_PACKET_EXTENSION_QUERY_INIT function](nf-netadapterpacket-net_packet_extension_query_init.md) | The NET_PACKET_EXTENSION_QUERY_INIT method initializes a NET_PACKET_EXTENSION_QUERY structure. |
| [NetPacketGetContextFromToken function](nf-netadapterpacket-netpacketgetcontextfromtoken.md) | The NetPacketGetContextFromToken method retrieves a NET_PACKET context based on a NET_PACKET_CONTEXT_TOKEN. |
| [NetPacketGetTypedContext function](nf-netadapterpacket-netpacketgettypedcontext.md) | Client drivers should not call this function directly. Instead, use NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME. |
| [NetRingBufferAdvanceNextPacket function](nf-netadapterpacket-netringbufferadvancenextpacket.md) | Increments the NextIndex value of the packet ring buffer, then returns a pointer to the packet at the new NextIndex value. |
| [NetRingBufferGetNextPacket function](nf-netadapterpacket-netringbuffergetnextpacket.md) | Returns a pointer to the packet in a packet ring buffer at the ring buffer's NextIndex index value. |
| [NetRingBufferGetPacketAtIndex function](nf-netadapterpacket-netringbuffergetpacketatindex.md) | Returns a pointer to the net packet at the specified index value of the packet ring buffer. |
| [NetRingBufferReturnAllPackets function](nf-netadapterpacket-netringbufferreturnallpackets.md) | The NetRingBufferReturnAllPackets method returns all packets in a datapath queue's packet ring buffer. |
| [NetRingBufferReturnCompletedPackets function](nf-netadapterpacket-netringbufferreturncompletedpackets.md) | Returns all packets in a datapath queue's packet ring buffer that have the Completed flag set. |
| [NetRingBufferReturnCompletedPacketsThroughIndex function](nf-netadapterpacket-netringbufferreturncompletedpacketsthroughindex.md) | Returns all packets in a datapath queue's packet ring buffer that have the Completed flag set, up to a specified range. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_PACKET_CONTEXT_ATTRIBUTES structure](ns-netadapterpacket-_net_packet_context_attributes.md) | The NET_PACKET_CONTEXT_ATTRIBUTES structure represents attributes for a NET_PACKET context space. |
| [_NET_PACKET_EXTENSION structure](ns-netadapterpacket-_net_packet_extension.md) | The NET_PACKET_EXTENSION structure contains packet extension information for either a net adapter or a datapath queue. |
| [_NET_PACKET_EXTENSION_QUERY structure](ns-netadapterpacket-_net_packet_extension_query.md) | The NET_PACKET_EXTENSION_QUERY structure represents a query for a packet extension. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE macro](nf-netadapterpacket-net_packet_context_attributes_init_type.md) | The NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE macro initializes a NetAdapterCx client driver's NET_PACKET_CONTEXT_ATTRIBUTES structure for a NET_PACKET and inserts driver-defined context information into the structure. |
| [NET_PACKET_DECLARE_CASTING_FUNCTION macro](nf-netadapterpacket-net_packet_declare_casting_function.md) | The NET_PACKET_DECLARE_CASTING_FUNCTION macro declares a casting function for a NET_PACKET context space. |
| [NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME macro](nf-netadapterpacket-net_packet_declare_context_type_with_name.md) | The NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME macro creates an accessor method with a specified name for a client driver's object-specific context space. Starting in NetAdapterCx 1.1, a second accessor method is also created with the same name as the first, but with the string "FromToken" appended. |
