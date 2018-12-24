---
UID: NS:netdatapathdescriptor._NET_DATAPATH_DESCRIPTOR
title: _NET_DATAPATH_DESCRIPTOR
description: The NET_DATAPATH_DESCRIPTOR structure describes a datapath queue's ring buffers.
tech.root: netvista
ms.assetid: 9b156fe0-5746-4628-9bc1-5973bf55710a
ms.date: 02/27/2018
ms.topic: struct
ms.keywords: _NET_DATAPATH_DESCRIPTOR, NET_DATAPATH_DESCRIPTOR, *PCNET_DATAPATH_DESCRIPTOR, 
req.header: netdatapathdescriptor.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_DATAPATH_DESCRIPTOR, *PCNET_DATAPATH_DESCRIPTOR
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netdatapathdescriptor.h
apiname: 
-	_NET_DATAPATH_DESCRIPTOR
product:
-	Windows
targetos: Windows
---

# _NET_DATAPATH_DESCRIPTOR structure

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_DATAPATH_DESCRIPTOR** structure describes a datapath queue's ring buffers.

## -struct-fields
 
### -field RingBuffer

A pointer an array of pointers to [**NET_RING_BUFFER**](../netringbuffer/ns-netringbuffer-_net_ring_buffer.md) structures.

## -remarks
Call [NetRxQueueGetDatapathDescriptor](../netrxqueue/nf-netrxqueue-netrxqueuegetdatapathdescriptor.md) or [NetTxQueueGetDatapathDescriptor](../nettxqueue/nf-nettxqueue-nettxqueuegetdatapathdescriptor.md) to get a queue's datapath descriptor. You can then use the descriptor to access the queue's ring buffers of packets or fragments with these macros:

- [NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER](nf-netdatapathdescriptor-net_datapath_descriptor_get_packet_ring_buffer.md)
- [NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER](nf-netdatapathdescriptor-net_datapath_descriptor_get_fragment_ring_buffer.md)
- [NET_PACKET_GET_FRAGMENT](nf-netdatapathdescriptor-net_packet_get_fragment.md)

The datapath descriptor is also used in other ring buffer manipulation methods defined in [Netadapterpacket.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netadapterpacket/):

- [NetRingBufferGetPacketAtIndex](../netadapterpacket/nf-netadapterpacket-netringbuffergetpacketatindex.md)
- [NetRingBufferGetNextPacket](../netadapterpacket/nf-netadapterpacket-netringbuffergetnextpacket.md)
- [NetRingBufferAdvanceNextPacket](../netadapterpacket/nf-netadapterpacket-netringbufferadvancenextpacket.md)
- [NetRingBufferReturnCompletedPacketsThroughIndex](../netadapterpacket/nf-netadapterpacket-netringbufferreturncompletedpacketsthroughindex.md)
- [NetRingBufferReturnAllPackets](../netadapterpacket/nf-netadapterpacket-netringbufferreturnallpackets.md)
- [NetRingBufferReturnCompletedPackets](../netadapterpacket/nf-netadapterpacket-netringbufferreturncompletedpackets.md)
- [NetPacketGetContextFromToken](../netadapterpacket/nf-netadapterpacket-netpacketgetcontextfromtoken.md)
- [NetPacketGetTypedContext](../netadapterpacket/nf-netadapterpacket-netpacketgettypedcontext.md)



## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
