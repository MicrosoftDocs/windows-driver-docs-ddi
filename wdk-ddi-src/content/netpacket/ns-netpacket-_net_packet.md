---
UID: NS:netpacket._NET_PACKET
title: _NET_PACKET
author: windows-driver-content
description: Represents a single network packet.
ms.assetid: c2fc32da-1979-45fe-96ed-0b79a48e58a3
ms.author: windowsdriverdev
ms.date: 07/13/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_PACKET, NET_PACKET, *PNET_PACKET, 
req.header: netpacket.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
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
product:
- Windows
---

# _NET_PACKET structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Represents a single network packet.

## -struct-fields

### -field FragmentOffset

The offset, in bytes, to the first [**NET_PACKET_FRAGMENT**](ns-netpacket-_net_packet_fragment.md) fragment structure in this packet's payload. This offset is from the beginning of the fragment ring buffer to the first fragment that belongs to this packet.

For receiving, client drivers are expected to set this value to the offset of the first **NET_PACKET_FRAGMENT** in the fragment ring.

### -field FragmentCount

The number of [**NET_PACKET_FRAGMENT**](ns-netpacket-_net_packet_fragment.md) structures that make up this packet.

For receiving, client drivers are expected to set this number.
 
### -field Layout

A [**NET_PACKET_LAYOUT**](ns-netpacket-_net_packet_layout.md) structure.

For transmit queues, if the host stack has enabled a task offload that uses a protocol header, specifies a read-only offset to each protocol field. For example, if TCP checksum offload is enabled, this member specifies the offset to the TCP header. Otherwise, this member is empty.

For receive queues, this member is reserved.
 
### -field IgnoreThisPacket

For receive queues, the client sets this bit to prevent the packet from being indicated to the host. For example, if the hardware encountered a DMA error while writing bytes into this the data buffer for this packet, the client can set this bit to drop the partial packet.

For transmit queues, this bit is read-only. If set, it indicates that the client should not transmit the packet.
 
### -field AdvancedOffloadRequested

Reserved. Do not read or write to this value.

### -field Completed

Specifies that this packet should be completed when the client calls [NetRingBufferReturnCompletedPackets](../netadapterpacket/nf-netadapterpacket-netringbufferreturncompletedpackets.md).

### -field NetPacketReserved0

Reserved. Client drivers must not read or write this value.

### -field NetPacketReserved1

Reserved. Client drivers must not read or write this value.

## -remarks

Each **NET_PACKET** structure represents a single network frame and contains basic metadata applicable to all packets, such as the framing layout. A **NET_PACKET** contains at least one [**NET_PACKET_FRAGMENT**](ns-netpacket-_net_packet_fragment.md) that describes the location in system memory where the packet data resides.

The **NET_PACKET** structure can be an element in a [**NET_RING_BUFFER**](../netringbuffer/ns-netringbuffer-_net_ring_buffer.md) structure.

You can optionally use [**NetRingBufferGetPacketAtIndex**](../netadapterpacket/nf-netadapterpacket-netringbuffergetpacketatindex.md) or [**NetRingBufferGetNextPacket**](../netadapterpacket/nf-netadapterpacket-netringbuffergetnextpacket.md) to obtain a **NET_PACKET** from a ring buffer.

## -see-also