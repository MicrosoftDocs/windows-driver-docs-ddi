---
UID: NC:netpacketqueue.EVT_PACKET_QUEUE_START
title: EVT_PACKET_QUEUE_START
author: windows-driver-content
description: The EvtPacketQueueStart callback function is implemented by the client driver to start the data path for a packet queue.
ms.assetid: 0B5CB7F0-C840-4138-8B22-4FE35120C7A5
ms.author: windowsdriverdev
ms.date: 07/17/2018
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
-	EVT_PACKET_QUEUE_START
product:
- Windows
targetos: Windows
---

# EVT_PACKET_QUEUE_START callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EvtPacketQueueStart* callback function is an optional callback that is implemented by the client driver to start the data path for a packet queue.

## -prototype

```C++
//Declaration

EVT_PACKET_QUEUE_START EvtPacketQueueStart; 

// Definition

VOID EvtPacketQueueStart 
(
	NETPACKETQUEUE PacketQueue
)
{...}

```

## -parameters

### -param PacketQueue

A handle to a packet queue.

## -returns

This callback does not return a value.

## -remarks

This is an optional callback. Register this callback function in your *EVT_NET_ADAPTER_CREATE_TX(RX)QUEUE* callback. Set the appropriate member of a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure after you initialize the structure with [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md), then call **NetTx(Rx)QueueCreate**.

In this callback, a client driver typically configures information that that its hardware needs for packet transmission or reception. Because this callback does not return a value and therefore should not fail, client drivers should perform actions such as resource allocation during queue creation. Therefore, this callback should be a light-weight function that executes quickly.

Client drivers will not receive calls to [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md), [*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md), or [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) until after *EvtPacketQueueStart* returns. In addition, *EvtPacketQueueStart* is called in the same execution context, or thread, as *EvtPacketQueueAdvance*, *EvtPacketQueueCancel*, and *EvtPacketQueueSetNotificationEnabled*, so client drivers do not need to synchronize between these callback functions for an individual queue instance.

When a queue starts, NetAdapterCx guarantees that **BeginIndex** == **NextIndex** == **0** for all of this queue's ring buffers. After start, the framework does not read or write **NextIndex** for packet ring buffers, so client drivers can either use it as needed or choose not to use it at all. **BeginIndex** is read by the framework but is not modified outside of *EvtPacketQueueStart*.

For more info and a diagram showing the NetAdapterCx data path polling model, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also

[*EVT_NET_ADAPTER_CREATE_RXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)

[*EVT_NET_ADAPTER_CREATE_TXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)

[*EVT_PACKET_QUEUE_STOP*](nc-netpacketqueue-evt_packet_queue_stop.md)