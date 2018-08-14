---
UID: NF:nettxqueue.NetTxQueueNotifyMoreCompletedPacketsAvailable
title: NetTxQueueNotifyMoreCompletedPacketsAvailable function
author: windows-driver-content
description: The client driver calls NetTxQueueNotifyMoreCompletedPacketsAvailable to resume queue operations after NetAdapterCx calls the client's EVT_TXQUEUE_SET_NOTIFICATION_ENABLED event callback routine.
ms.assetid: 930bb60a-6ce0-4af3-b78e-160a36fc998d
ms.author: windowsdriverdev
ms.date: 07/13/2018
ms.topic: function
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
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	nettxqueue.h
apiname: 
-	NetTxQueueNotifyMoreCompletedPacketsAvailable
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetTxQueueNotifyMoreCompletedPacketsAvailable function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The client driver calls **NetTxQueueNotifyMoreCompletedPacketsAvailable** to resume queue operations after NetAdapterCx calls the client's [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) event callback routine.

## -parameters

### -param TxQueue

A handle to a net transmit queue.

## -returns

This method does not return a value.

## -remarks

This method should only be called when polling is disabled.

After NetAdapterCx calls a client driver's [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) event callback routine with *NotificationEnabled* set to **TRUE**, the client enables the queue's hardware interrupt. When the device generates a hardware interrupt, the client typically calls **NetTxQueueNotifyMoreCompletedPacketsAvailable** from its *[EVT_WDF_INTERRUPT_DPC](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc.md) callback function, after it completes a pending [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) in the transmit queue's [NET_RING_BUFFER](../netringbuffer/ns-netringbuffer-_net_ring_buffer.md).

The client should only call **NetTxQueueNotifyMoreCompletedPacketsAvailable** once per enabling of the notification. Do not call **NetTxQueueNotifyMoreCompletedPacketsAvailable** if NetAdapterCx calls *[EVT_TXQUEUE_SET_NOTIFICATION_ENABLED](nc-nettxqueue-evt_txqueue_set_notification_enabled.md)* with *NotificationEnabled* set to **FALSE**.

The client should only call **NetTxQueueNotifyMoreCompletedPacketsAvailable** once per enabling of the notification. Do not call **NetTxQueueNotifyMoreCompletedPacketsAvailable** if NetAdapterCx calls [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) with *NotificationEnabled* set to **FALSE**.


## -see-also

[*EVT_PACKET_QUEUE_ADVANCE*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)