---
UID: NF:netrxqueue.NetRxQueueNotifyMoreReceivedPacketsAvailable
title: NetRxQueueNotifyMoreReceivedPacketsAvailable function (netrxqueue.h)
description: The client driver calls NetRxQueueNotifyMoreReceivedPacketsAvailable to resume queue operations after NetAdapterCx calls the client's EVT_RXQUEUE_SET_NOTIFICATION_ENABLED event callback routine.
tech.root: netvista
ms.assetid: 81463460-f494-4265-a557-134a50a91d52
ms.date: 11/06/2018
keywords: ["NetRxQueueNotifyMoreReceivedPacketsAvailable function"]
ms.keywords: NetRxQueueNotifyMoreReceivedPacketsAvailable
req.header: netrxqueue.h
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
targetos: Windows
f1_keywords:
 - NetRxQueueNotifyMoreReceivedPacketsAvailable
 - netrxqueue/NetRxQueueNotifyMoreReceivedPacketsAvailable
topictype:
 - apiref
apitype:
 - HeaderDef
apilocation:
 - netrxqueue.h
apiname:
 - NetRxQueueNotifyMoreReceivedPacketsAvailable
---

# NetRxQueueNotifyMoreReceivedPacketsAvailable function


## -description

The client driver calls **NetRxQueueNotifyMoreReceivedPacketsAvailable** to resume queue operations after NetAdapterCx calls the client's [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) event callback routine.

## -parameters

### -param RxQueue

A handle to a net receive queue object.

## -remarks

This function should only be called when polling is disabled.

After NetAdapterCx calls a client driver's [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) event callback routine with *NotificationEnabled* set to **TRUE**, the client enables the queue's hardware interrupt. When the device generates a hardware interrupt, the client typically calls **NetRxQueueNotifyMoreReceivedPacketsAvailable** from its [*EVT_WDF_INTERRUPT_DPC*](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc.md) callback function, after it completes a pending [**NET_PACKET**](../packet/ns-packet-_net_packet.md) in the receive queue's [**NET_RING**](../ring/ns-ring-_net_ring.md).

The client should only call **NetRxQueueNotifyMoreReceivedPacketsAvailable** once per enabling of the notification. If the most recent call to [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) has *NotificationEnabled* set to **FALSE**, the client should avoid invoking **NetRxQueueNotifyMoreReceivedPacketsAvailable**. Because NetAdapterCx invokes *EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED* repeatedly, the client may miss a few cases and call **NetRxQueueNotifyMoreReceivedPacketsAvailable** when *NotificationEnabled* is set to **FALSE**. In these cases, the call will be a no-op.

## -see-also

[*EVT_PACKET_QUEUE_ADVANCE*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)

