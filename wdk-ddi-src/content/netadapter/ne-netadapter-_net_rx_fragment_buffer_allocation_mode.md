---
UID: NE:netadapter._NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE
title: _NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE (netadapter.h)
description: The NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE enumeration identifies how the operating system should allocate NET_PACKET_FRAGMENT receive buffers for a net adapter client driver's receive queues.
tech.root: netvista
ms.assetid: b7ce305a-ea72-4461-9d91-c4e3fb84eb8a
ms.date: 02/15/2018
ms.topic: enum
ms.keywords: _NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE, NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- _NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE
product:
- Windows
targetos: Windows
---

# _NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE** enumeration identifies how the operating system should allocate [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive buffers for a net adapter client driver's receive queues.

## -enum-fields

### -field NetRxFragmentBufferAllocationModeSystem : 
The operating system allocates [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive buffers on behalf of the client driver.

### -field NetRxFragmentBufferAllocationModeDriver : 
The operating system never allocates [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive buffers. The client driver is responsible for buffer allocation.

## -remarks
This enumeration is a value of the [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure. Together with [NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE](ne-netadapter-_net_rx_fragment_buffer_attachment_mode.md), it specifies how a net adapter client driver would like to configure its receive queue fragment buffers. For more information, see [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md).



## -see-also

[NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md)
