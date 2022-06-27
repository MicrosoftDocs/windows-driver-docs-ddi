---
UID: NS:netpacketqueue._NET_PACKET_QUEUE_CONFIG
title: _NET_PACKET_QUEUE_CONFIG (netpacketqueue.h)
description: The NET_PACKET_QUEUE_CONFIG structure describes the configuration options for a NetAdapterCx client driver's packet queue.
tech.root: netvista
ms.date: 03/23/2022
keywords: ["NET_PACKET_QUEUE_CONFIG structure"]
ms.keywords: _NET_PACKET_QUEUE_CONFIG, NET_PACKET_QUEUE_CONFIG, *PNET_PACKET_QUEUE_CONFIG,
req.header: netpacketqueue.h
req.include-header: netadaptercx.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_PACKET_QUEUE_CONFIG, *PNET_PACKET_QUEUE_CONFIG
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NET_PACKET_QUEUE_CONFIG
 - netpacketqueue/_NET_PACKET_QUEUE_CONFIG
 - NET_PACKET_QUEUE_CONFIG
 - netpacketqueue/NET_PACKET_QUEUE_CONFIG
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netpacketqueue.h
api_name:
 - _NET_PACKET_QUEUE_CONFIG
 - NET_PACKET_QUEUE_CONFIG
---

# _NET_PACKET_QUEUE_CONFIG structure


## -description

The **NET_PACKET_QUEUE_CONFIG** structure describes the configuration options for a NetAdapterCx client driver's packet queue.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field EvtStart

A pointer to the client driver's [*EVT_PACKET_QUEUE_START*](nc-netpacketqueue-evt_packet_queue_start.md) event callback function for this packet queue. This callback function is required.

### -field EvtStop

A pointer to the client driver's [*EVT_PACKET_QUEUE_STOP*](nc-netpacketqueue-evt_packet_queue_stop.md) event callback function for this packet queue. This callback function is required.

### -field EvtAdvance

A pointer to the client driver's [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) event callback function for this packet queue. This callback function is required.

### -field EvtSetNotificationEnabled

A pointer to the client driver's [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) event callback function for this packet queue. This callback function is required.

### -field EvtCancel

A pointer to the client driver's [*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md) event callback function for this packet queue. This callback function is required.

### -field ExecutionContext

A NETEXECUTIONCONTEXT object.

## -remarks

Call [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md) to initialize this structure.

The **NET_PACKET_QUEUE_CONFIG** structure is an input parameter to [**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md) and [**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md). The client must use [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md) to initialize this structure before calling **NetTx(Rx)QueueCreate**.

## -see-also

[**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

