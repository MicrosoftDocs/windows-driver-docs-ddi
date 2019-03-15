---
UID: NS:netringbuffer._NET_RING_BUFFER
title: _NET_RING_BUFFER (netringbuffer.h)
description: Specifies a buffer comprised of one or more NET_PACKET structures.
tech.root: netvista
ms.assetid: 66232a58-73fc-4f3a-9682-0dd9f10dc901
ms.date: 02/09/2018
ms.topic: struct
ms.keywords: _NET_RING_BUFFER, NET_RING_BUFFER, *PNET_RING_BUFFER, 
req.header: netringbuffer.h
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
req.typenames: NET_RING_BUFFER, *PNET_RING_BUFFER
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- netringbuffer.h
apiname: 
- NET_RING_BUFFER
product:
- Windows
targetos: Windows
product:
- Windows
---

# _NET_RING_BUFFER structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Specifies a buffer comprised of one or more [**NET_PACKET**](../netpacket/ns-netpacket-_net_packet.md) or [**NET_PACKET_FRAGMENT**](../netpacket/ns-netpacket-_net_packet_fragment.md) structures.

## -struct-fields

### -field OSReserved1
Reserved. Client drivers must not read or write to this value.
 
### -field ElementStride
A read-only byte offset from the start of one [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) to the start of the next. Use `((BYTE*)p + ElementStride)` to obtain the address of the next element.
 
### -field NumberOfElements
A read-only value that indicates the number of packets in the ring buffer, which is always a power of two, and greater than one.
 
### -field ElementIndexMask
A read-only UINT32 mask that is defined as (**NumberOfElements** - 1). The client can use this value to calculate an index that wraps around the ring buffer. Use the identity `(x % NumberofElements) == (x & ElementIndexMask)`.
 
### -field BeginIndex
Specifies the index of the first element owned by the client driver in the inclusive range [0, **NumberOfElements** - 1]. While a client driver can modify this value directly, it typically uses helper routines like [NetRingBufferReturnCompletedPackets](../netadapterpacket/nf-netadapterpacket-netringbufferreturncompletedpackets.md) instead.
 
### -field NextIndex
Specifies the index of the next element that needs processing. For optional use by the client driver. While a client driver can modify this value directly, it typically calls [NetRingBufferAdvanceNextPacket](../netadapterpacket/nf-netadapterpacket-netringbufferadvancenextpacket.md) instead.
 
### -field EndIndex
Specifies the read-only index of the last element that is owned by the client driver in the inclusive range [0, **NumberOfElements** - 1].
 
### -field NetAdapterScratch
A pointer to a buffer that the client driver may use for any purpose.
 
### -field OSReserved2
Reserved. Client drivers must not read or write to this value.
 
### -field Buffer
A byte array that contains the elements in the ring buffer. Typically, a client driver calls [NetRingBufferGetPacketAtIndex](../netadapterpacket/nf-netadapterpacket-netringbuffergetpacketatindex.md) to access packets in the ring buffer.

## -remarks
The **NET_RING_BUFFER** structure is a generic ring buffer, optimized for efficient access from a single thread. A **NET_RING_BUFFER** contains [**NET_PACKET**](../netpacket/ns-netpacket-_net_packet.md) or [**NET_PACKET_FRAGMENT**](../netpacket/ns-netpacket-_net_packet_fragment.md) elements.

For more info about packet and fragment ring buffers, see [Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions#storage-of-packet-descriptors).

For more info about using the packet ring buffer, see [Using the ring buffer](https://docs.microsoft.com/windows-hardware/drivers/netcx/using-the-ring-buffer).

## -see-also
