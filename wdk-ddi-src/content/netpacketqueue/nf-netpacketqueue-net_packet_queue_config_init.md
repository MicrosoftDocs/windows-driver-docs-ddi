---
UID: NF:netpacketqueue.NET_PACKET_QUEUE_CONFIG_INIT
title: NET_PACKET_QUEUE_CONFIG_INIT function (netpacketqueue.h)
description: The NET_PACKET_QUEUE_CONFIG_INIT method initializes a NET_PACKET_QUEUE_CONFIG structure.
tech.root: netvista
ms.assetid: 5dd456ed-b2ec-4a60-8a43-0803a87eac84
ms.date: 07/16/2018
ms.topic: function
ms.keywords: NET_PACKET_QUEUE_CONFIG_INIT
req.header: netpacketqueue.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: netadaptercxstub.lib
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
-	LibDef
api_location: 
-	netadaptercxstub.lib
api_name: 
-	NET_PACKET_QUEUE_CONFIG_INIT
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# NET_PACKET_QUEUE_CONFIG_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_PACKET_QUEUE_CONFIG_INIT** method initializes a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure.

## -parameters

### -param Config

A pointer to the driver-allocated [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure to initialize.

### -param EvtAdvance

A pointer to the client driver's implementation of the [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) callback function for this packet queue.

### -param EvtSetNotificationEnabled

A pointer to the client driver's implementation of the [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_advance.md) callback function for this packet queue.

### -param EvtCancel

A pointer to the client driver's implementation of the [*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_advance.md) callback function for this packet queue.

## -returns

This method does not return a value.

## -remarks

Client drivers must call this method to initialize a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure before calling [**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md) or [**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) to create a packet queue.

## -see-also

[**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)
