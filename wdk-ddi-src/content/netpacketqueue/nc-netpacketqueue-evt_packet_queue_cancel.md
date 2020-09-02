---
UID: NC:netpacketqueue.EVT_PACKET_QUEUE_CANCEL
title: EVT_PACKET_QUEUE_CANCEL (netpacketqueue.h)
description: The EvtPacketQueueCancel callback function is implemented by the client driver to handle operations that must be performed before a packet queue is deleted.
tech.root: netvista
ms.assetid: 92d4e786-7fac-43c2-910a-1c7c5873855f
ms.date: 01/24/2019
keywords: ["EVT_PACKET_QUEUE_CANCEL callback function"]
req.header: netpacketqueue.h
req.include-header: netadaptercx.h 
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - EVT_PACKET_QUEUE_CANCEL
 - netpacketqueue/EVT_PACKET_QUEUE_CANCEL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - netpacketqueue.h
api_name:
 - EVT_PACKET_QUEUE_CANCEL
---

# EVT_PACKET_QUEUE_CANCEL callback function


## -description

The *EvtPacketQueueCancel* callback function is implemented by the client driver to handle operations that must be performed before a packet queue is deleted.

## -parameters

### -param PacketQueue

A handle to a packet queue.

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

## -remarks

Register this callback function in your *EVT_NET_ADAPTER_CREATE_TX(RX)QUEUE* callback. Set the appropriate member of a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure when you are initializing the structure with [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md), then call **NetTx(Rx)QueueCreate**.

NetAdapterCx serializes this callback function along with the packet queue's [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) and [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) callback functions.

For more info and a diagram showing the NetAdapterCx data path polling model, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also

[*EVT_NET_ADAPTER_CREATE_RXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)

[*EVT_NET_ADAPTER_CREATE_TXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[*EVT_PACKET_QUEUE_START*](nc-netpacketqueue-evt_packet_queue_start.md)

[*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)

[*EVT_PACKET_QUEUE_STOP*](nc-netpacketqueue-evt_packet_queue_stop.md)

