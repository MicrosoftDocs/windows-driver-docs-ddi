---
UID: NE:netadapter._NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
title: _NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
author: windows-driver-content
description: The NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE enumeration identifies how the operating system should pre-attach NET_PACKET_FRAGMENT buffers to NET_PACKETs for a net adapter client driver's receive queues.
ms.assetid: 887f68a8-1154-492e-8af3-0280a8637ef5
ms.author: windowsdriverdev
ms.date: 02/15/2018
ms.topic: enum
ms.keywords: _NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE, NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	_NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
product: Windows
targetos: Windows
---

# _NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE** enumeration identifies how the operating system should pre-attach [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) buffers to [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md)s for a net adapter client driver's receive queues.

## -enum-fields

### -field NetRxFragmentBufferAttachmentModeSystem : 
The operating system attaches receive [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md)s to [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md)s automatically. This value is valid **only** when receive fragment buffer allocation, identified by the [NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE](ne-netadapter-_net_rx_fragment_buffer_allocation_mode.md) enumeration, is also set to **NetRxFragmentBufferAllocationModeSystem**.

### -field NetRxFragmentBufferAttachmentModeDriver : 
The client driver is responsible for attaching [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive buffers to [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md)s.

## -remarks
This enumeration is a value of the [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure. Together with [NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE](ne-netadapter-_net_rx_fragment_buffer_allocation_mode.md), it specifies how a net adapter client driver would like to configure its receive queue fragment buffers. For more information, see [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md).



## -see-also