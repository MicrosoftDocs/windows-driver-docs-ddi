---
UID: NC:netpacketqueue.EVT_PACKET_QUEUE_STOP
title: EVT_PACKET_QUEUE_STOP (netpacketqueue.h)
description: The EvtPacketQueueStop callback function is implemented by the client driver to stop the data path for a packet queue before it is deleted.
tech.root: netvista
ms.assetid: 42ae223c-fe68-48ff-b086-92d8a406d4b6
ms.date: 07/18/2018
keywords: ["EVT_PACKET_QUEUE_STOP callback function"]
f1_keywords:
 - "netpacketqueue/EVT_PACKET_QUEUE_STOP"
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
- apiref
api_type: 
- UserDefined
api_location: 
- netpacketqueue.h
api_name: 
- EVT_PACKET_QUEUE_STOP
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_PACKET_QUEUE_STOP callback function

## -description



The *EvtPacketQueueStop* callback function is an optional callback that is implemented by the client driver to stop the data path for a packet queue.

## -prototype

```C++
//Declaration

EVT_PACKET_QUEUE_STOP EvtPacketQueueStop; 

// Definition

VOID EvtPacketQueueStop 
(
	NETPACKETQUEUE PacketQueue
)
{...}

```

## -parameters

### -param PacketQueue

A handle to a packet queue.

## -remarks

This is an optional callback. Register this callback function in your *EVT_NET_ADAPTER_CREATE_TX(rxQueueContext)QUEUE* callback. Set the appropriate member of a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure after you initialize the structure with [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md), then call **NetTx(rxQueueContext)QueueCreate**.

This callback does not return a value and therefore should not fail, so this callback should be a light-weight function that executes quickly.

Client drivers will not receive calls to [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md), [*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md), or [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) after *EvtPacketQueueStop* returns. In addition, *EvtPacketQueueStop* is called in the same execution context, or thread, as *EvtPacketQueueAdvance*, *EvtPacketQueueCancel*, and *EvtPacketQueueSetNotificationEnabled*, so client drivers do not need to synchronize between these callback functions for an individual queue instance.

For more info and a diagram showing the NetAdapterCx data path polling model, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also

[*EVT_NET_ADAPTER_CREATE_RXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)

[*EVT_NET_ADAPTER_CREATE_TXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[*EVT_PACKET_QUEUE_START*](nc-netpacketqueue-evt_packet_queue_start.md)

[*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)

[*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md)
