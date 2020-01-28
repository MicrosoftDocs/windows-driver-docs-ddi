---
UID: NF:nettxqueue.NetTxQueueNotifyMoreCompletedPacketsAvailable
title: NetTxQueueNotifyMoreCompletedPacketsAvailable function (nettxqueue.h)
description: The client driver calls NetTxQueueNotifyMoreCompletedPacketsAvailable to resume queue operations after NetAdapterCx calls the client's EVT_TXQUEUE_SET_NOTIFICATION_ENABLED event callback routine.
tech.root: netvista
ms.assetid: 930bb60a-6ce0-4af3-b78e-160a36fc998d
ms.date: 07/13/2018
f1_keywords:
 - "nettxqueue/NetTxQueueInitGetQueueId"
ms.keywords: NetTxQueueNotifyMoreCompletedPacketsAvailable
req.header: nettxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= HIGH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- nettxqueue.h
apiname: 
- NetTxQueueNotifyMoreCompletedPacketsAvailable
targetos: Windows
product:
- Windows
---

# NetTxQueueNotifyMoreCompletedPacketsAvailable function


## -description



The client driver calls **NetTxQueueNotifyMoreCompletedPacketsAvailable** to resume queue operations after NetAdapterCx calls the client's [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) event callback routine.

## -parameters

### -param TxQueue

A handle to a net transmit queue.

## -remarks

This method should only be called when polling is disabled.

After NetAdapterCx calls a client driver's [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) event callback routine with *NotificationEnabled* set to **TRUE**, the client enables the queue's hardware interrupt. When the device generates a hardware interrupt, the client typically calls **NetTxQueueNotifyMoreCompletedPacketsAvailable** from its *[EVT_WDF_INTERRUPT_DPC](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc.md) callback function, after it completes a pending [NET_PACKET](../packet/ns-packet-_net_packet.md) in the transmit queue's [**NET_RING**](../ring/ns-ring-_net_ring.md).

The client should only call **NetTxQueueNotifyMoreCompletedPacketsAvailable** once per enabling of the notification. Do not call **NetTxQueueNotifyMoreCompletedPacketsAvailable** if NetAdapterCx calls *[EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)* with *NotificationEnabled* set to **FALSE**.

The client should only call **NetTxQueueNotifyMoreCompletedPacketsAvailable** once per enabling of the notification. Do not call **NetTxQueueNotifyMoreCompletedPacketsAvailable** if NetAdapterCx calls [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) with *NotificationEnabled* set to **FALSE**.


## -see-also

[*EVT_PACKET_QUEUE_ADVANCE*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)
