---
UID: NF:netdatapathdescriptor.NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER
title: NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER macro (netdatapathdescriptor.h)
description: The NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER macro retrieves a datapath queue's packet ring buffer.
tech.root: netvista
ms.date: 02/27/2018
keywords: ["NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER macro"]
f1_keywords:
 - "netdatapathdescriptor/NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER"
 - "NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER"
ms.keywords: NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER
req.header: netdatapathdescriptor.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib: netdatapathdescriptor.h
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netdatapathdescriptor.h
api_name: 
- NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER
targetos: Windows

---

# NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER macro


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER** macro retrieves a datapath queue's packet ring buffer.

## -parameters

### -param rbs
A pointer to the queue's [NET_DATAPATH_DESCRIPTOR](ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

## -remarks
To retrieve a queue's ring buffer of [NET_PACKET](../packet/ns-packet-_net_packet.md)s, first call **NetRx(Tx)QueueGetDatapathDescriptor** to get the queue's datapath descriptor, then call this macro with the descriptor.



## -see-also

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
