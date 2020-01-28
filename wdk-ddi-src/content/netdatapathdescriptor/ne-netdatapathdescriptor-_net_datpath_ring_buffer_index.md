---
UID: NE:netdatapathdescriptor._NET_DATPATH_RING_BUFFER_INDEX
title: _NET_DATPATH_RING_BUFFER_INDEX (netdatapathdescriptor.h)
description: The NET_DATAPATH_RING_BUFFER_INDEX enumeration defines indices in a datapath queue's array of ring buffers.
tech.root: netvista
ms.assetid: 19cc4a99-3419-4710-85f0-c7b9932f6daa
ms.date: 02/27/2018
f1_keywords:
 - "netdatapathdescriptor/_NET_DATPATH_RING_BUFFER_INDEX"
ms.keywords: _NET_DATPATH_RING_BUFFER_INDEX, NET_DATPATH_RING_BUFFER_INDEX, 
req.header: netdatapathdescriptor.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: NET_DATPATH_RING_BUFFER_INDEX
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netdatapathdescriptor.h
api_name: 
- _NET_DATPATH_RING_BUFFER_INDEX
product:
- Windows
targetos: Windows
---

# _NET_DATPATH_RING_BUFFER_INDEX enumeration

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_DATAPATH_RING_BUFFER_INDEX** enumeration defines indices in a datapath queue's array of ring buffers.

## -enum-fields

### -field NET_DATPATH_RING_BUFFER_INDEX_PACKET : 
The index of the queue's ring buffer of [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md)s.

### -field NET_DATPATH_RING_BUFFER_INDEX_FRAGMENT : 
The index of the queue's ring buffer of [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md)s.

## -remarks
NIC client drivers should not use this enumeration directly. Instead, they should call the appropriate macro to access a particular ring buffer:

- [NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER](nf-netdatapathdescriptor-net_datapath_descriptor_get_packet_ring_buffer.md)
- [NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER](nf-netdatapathdescriptor-net_datapath_descriptor_get_fragment_ring_buffer.md)



## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[NET_DATAPATH_DESCRIPTOR](ns-netdatapathdescriptor-_net_datapath_descriptor.md)

[NET_RING_BUFFER](../netringbuffer/ns-netringbuffer-_net_ring_buffer.md)
