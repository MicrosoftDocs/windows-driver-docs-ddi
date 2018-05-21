---
UID: NF:nettxqueue.NET_TXQUEUE_CONFIG_INIT
title: NET_TXQUEUE_CONFIG_INIT function
author: windows-driver-content
description: Initializes a NET_TXQUEUE_CONFIG structure.
ms.assetid: 774148ab-69d6-4461-af87-2cbad54495a6
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NET_TXQUEUE_CONFIG_INIT
req.header: nettxqueue.h
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
-	nettxqueue.h
apiname: 
-	NET_TXQUEUE_CONFIG_INIT
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NET_TXQUEUE_CONFIG_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Initializes a [NET_TXQUEUE_CONFIG](ns-nettxqueue-_net_txqueue_config.md) structure.

## -parameters

### -param NetTxQueueConfig
A pointer to the driver-allocated [NET_TXQUEUE_CONFIG](ns-nettxqueue-_net_txqueue_config.md) structure.

### -param EvtTxQueueAdvance
A pointer to the driver's *[EVT_TXQUEUE_ADVANCE](nc-nettxqueue-evt_txqueue_advance.md)* callback function.

### -param EvtTxQueueSetNotificationEnabled
A pointer to the driver's *[EVT_TXQUEUE_SET_NOTIFICATION_ENABLED](nc-nettxqueue-evt_txqueue_set_notification_enabled.md)* callback function.

### -param EvtTxQueueCancel
A pointer to the driver's *[EVT_TXQUEUE_CANCEL](nc-nettxqueue-evt_txqueue_cancel.md)* callback function.

## -returns
This method does not return a value.

## -remarks
The minimum NetAdapterCx version for **NET_TXQUEUE_CONFIG_INIT** is 1.0.

## -see-also