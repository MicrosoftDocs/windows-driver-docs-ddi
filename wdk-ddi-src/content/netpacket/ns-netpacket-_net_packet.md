---
UID: NS:netpacket._NET_PACKET
title: _NET_PACKET
author: windows-driver-content
description: Represents a single network packet.
ms.assetid: c2fc32da-1979-45fe-96ed-0b79a48e58a3
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_PACKET, NET_PACKET, *PNET_PACKET, 
req.header: netpacket.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_PACKET, *PNET_PACKET
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netpacket.h
apiname: 
-	NET_PACKET
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_PACKET structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Represents a single network packet.

## -struct-fields

### -field FragmentOffset
The offset, in bytes, to the first [NET_PACKET_FRAGMENT](ns-netpacket-_net_packet_fragment.md) fragment structure in this packet's payload. This offset is from the beginning of the fragment ring buffer to the first fragment that belongs to this packet. See the **LastFragmentOfFrame** member of the **NET_PACKET_FRAGMENT** structure to determine if this packet is associated with additional fragments.

### -field FragmentValid
Describes whether this packet has at least one valid [NET_PACKET_FRAGMENT](ns-netpacket-_net_packet_fragment.md) structure attached to it. Use the **NET_PACKET_GET_FRAGMENT_VALID** macro to determine if a **NET_PACKET** is empty (has no fragment buffers attached).
 
### -field Layout
A [NET_PACKET_LAYOUT](ns-netpacket-_net_packet_layout.md) structure.

For transmit queues, if the host stack has enabled a task offload that uses a protocol header, specifies a read-only offset to each protocol field. For example, if TCP checksum offload is enabled, this member specifies the offset to the TCP header. Otherwise, this member is empty.

For receive queues, this member is reserved.

### -field Reserved4
Reserved. Do not read or write to this value.
 
### -field IgnoreThisPacket
For receive queues, the client sets this bit to prevent the packet from being indicated to the host. For example, if the hardware encountered a DMA error while writing bytes into this the data buffer for this packet, the client can set this bit to drop the partial packet.

For transmit queues, this bit is read-only. If set, it indicates that the client should not transmit the packet.
 
### -field AdvancedOffloadRequested
Reserved. Do not read or write to this value.

### -field Reserved1
Reserved. Do not read or write to this value.

### -field Hash
Reserved. Do not read or write to this value.

## -remarks
Each **NET_PACKET** structure represents a single network frame.

The **NET_PACKET** structure can be an element in a [NET_RING_BUFFER](../netringbuffer/ns-netringbuffer-_net_ring_buffer.md) structure.

You can optionally use [NetRingBufferGetPacketAtIndex](../netadapterpacket/nf-netadapterpacket-netringbuffergetpacketatindex.md) or [NetRingBufferGetNextPacket](../netadapterpacket/nf-netadapterpacket-netringbuffergetnextpacket.md) to obtain a **NET_PACKET** from a ring buffer.



## -see-also