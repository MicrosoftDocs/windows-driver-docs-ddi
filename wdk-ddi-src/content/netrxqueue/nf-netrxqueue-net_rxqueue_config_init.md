---
UID: NF:netrxqueue.NET_RXQUEUE_CONFIG_INIT
title: NET_RXQUEUE_CONFIG_INIT function
author: windows-driver-content
description: Initializes a NET_RXQUEUE_CONFIG structure.
ms.assetid: cc6abfef-77a5-4680-9bda-621955910df8
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NET_RXQUEUE_CONFIG_INIT
req.header: netrxqueue.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
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
req.alt-api:
req.alt-loc:
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrxqueue.h
apiname: 
-	NET_RXQUEUE_CONFIG_INIT
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NET_RXQUEUE_CONFIG_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Initializes a [NET_RXQUEUE_CONFIG](ns-netrxqueue-_net_rxqueue_config.md) structure.

## -parameters

### -param NetRxQueueConfig
A pointer to the driver-allocated [NET_RX_QUEUE_CONFIG](ns-netrxqueue-_net_rxqueue_config.md) structure.

### -param EvtRxQueueAdvance
A pointer to the driver's *[EVT_RXQUEUE_ADVANCE](nc-netrxqueue-evt_rxqueue_advance.md)* callback function.

### -param EvtRxQueueSetNotificationEnabled
A pointer to the driver's *[EVT_RXQUEUE_SET_NOTIFICATION_ENABLED](nc-netrxqueue-evt_rxqueue_set_notification_enabled.md)* callback function.

### -param EvtRxQueueCancel
A pointer to the driver's *[EVT_RXQUEUE_CANCEL](nc-netrxqueue-evt_rxqueue_cancel.md)* callback function.

## -returns
This method does not return a value.

## -remarks


## -see-also