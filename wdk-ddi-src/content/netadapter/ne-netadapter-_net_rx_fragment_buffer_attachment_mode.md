---
UID: NE:netadapter._NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
title: _NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE (netadapter.h)
description: The NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE enumeration identifies how the operating system should pre-attach NET_PACKET_FRAGMENT buffers to NET_PACKETs for a net adapter client driver's receive queues.
tech.root: netvista
ms.assetid: 887f68a8-1154-492e-8af3-0280a8637ef5
ms.date: 02/15/2018
keywords: ["NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE enumeration"]
ms.keywords: _NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE, NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE,
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
targetos: Windows
f1_keywords:
 - _NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
 - netadapter/_NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
 - NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
 - netadapter/NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
topictype:
 - apiref
apitype:
 - HeaderDef
apilocation:
 - netadapter.h
apiname:
 - _NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE
---

# _NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE enumeration


## -description

The **NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE** enumeration identifies how the operating system should pre-attach [NET_FRAGMENT](../fragment/ns-fragment-_net_fragment.md) buffers to [NET_PACKET](../packet/ns-packet-_net_packet.md)s for a net adapter client driver's receive queues.

## -enum-fields

### -field NetRxFragmentBufferAttachmentModeSystem : 

The operating system attaches receive [NET_FRAGMENT](../fragment/ns-fragment-_net_fragment.md)s to [NET_PACKET](../packet/ns-packet-_net_packet.md)s automatically. This value is valid **only** when receive fragment buffer allocation, identified by the [NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE](ne-netadapter-_net_rx_fragment_buffer_allocation_mode.md) enumeration, is also set to **NetRxFragmentBufferAllocationModeSystem**.

### -field NetRxFragmentBufferAttachmentModeDriver : 

The client driver is responsible for attaching [NET_FRAGMENT](../fragment/ns-fragment-_net_fragment.md) receive buffers to [NET_PACKET](../packet/ns-packet-_net_packet.md)s.

## -remarks

This enumeration is a value of the [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure. Together with [NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE](ne-netadapter-_net_rx_fragment_buffer_allocation_mode.md), it specifies how a net adapter client driver would like to configure its receive queue fragment buffers. For more information, see [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md).

## -see-also

