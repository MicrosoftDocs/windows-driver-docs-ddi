---
UID: NC:netpacketqueue.EVT_PACKET_QUEUE_CANCEL
title: EVT_PACKET_QUEUE_CANCEL
author: windows-driver-content
description: The EvtPacketQueueCancel callback function is implemented by the client driver to handle operations that must be performed before a packet queue is deleted.
tech.root: netvista
ms.assetid: 92d4e786-7fac-43c2-910a-1c7c5873855f
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netpacketqueue.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib:
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	netpacketqueue.h
api_name: 
-	EVT_PACKET_QUEUE_CANCEL
product:
- Windows
targetos: Windows
---

# EVT_PACKET_QUEUE_CANCEL callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EvtPacketQueueCancel* callback function is implemented by the client driver to handle operations that must be performed before a packet queue is deleted.

## -prototype

```C++
//Declaration

EVT_PACKET_QUEUE_CANCEL EvtPacketQueueCancel; 

// Definition

VOID EvtPacketQueueCancel 
(
	NETPACKETQUEUE PacketQueue
)
{...}

```

## -parameters

### -param PacketQueue

A handle to a packet queue.

## -returns

This callback function does not return a value.

## -remarks

Register this callback function in your *EVT_NET_ADAPTER_CREATE_TX(RX)QUEUE* callback. Set the appropriate member of a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure when you are initializing the structure with [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md), then call **NetTx(Rx)QueueCreate**.

NetAdapterCx serializes this callback function along with the packet queue's [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) and [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) callback functions.

For more info and a diagram showing the NetAdapterCx data path polling model, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

### Transmit queue remarks

In your *EVT_PACKET_CANCEL* callback function for a transmit queue, you have an opportunity to complete any outstanding transmit packets. Unlike with a receive queue, you not required to do so. If you leave outstanding packets, NetAdapterCx calls your [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) for the transmit queue, where you process them as part of your regular operation.

If your hardware supports cancelling in-flight transmits, you should also advance the ring buffer's **BeginIndex** past all cancelled packets. If your hardware does not support cancellation, this callback can return without taking action.

For more info about ring buffer usage, see [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) and [Using the ring buffer](https://docs.microsoft.com/windows-hardware/drivers/netcx/using-the-ring-buffer).

### Receive queue remarks and example

In your *EVT_PACKET_QUEUE_CANCEL* callback function for a receive queue, you must complete any outstanding receive packets. If you do not return all packets, the operating system does not delete the queue, and NetAdapterCx stops calling your callbacks for the queue. To return packets, call the [NetRingBufferReturnAllPackets](../netadapterpacket/nf-netadapterpacket-netringbufferreturnallpackets.md) method.

For example:

```C++
VOID
EvtRxQueueCancel(NETRXQUEUE RxQueue)
{
    PCNET_DATAPATH_DESCRIPTOR descriptor = NetRxQueueGetDatapathDescriptor(RxQueue);

    NetRingBufferReturnAllPackets(descriptor);
}
```

For additional example code demonstrating ring buffer usage, see [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md).

## -see-also

[*EVT_NET_ADAPTER_CREATE_RXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)

[*EVT_NET_ADAPTER_CREATE_TXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[*EVT_PACKET_QUEUE_START*](nc-netpacketqueue-evt_packet_queue_start.md)

[*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)

[*EVT_PACKET_QUEUE_STOP*](nc-netpacketqueue-evt_packet_queue_stop.md)
