---
UID: NS:nettxqueue._NET_TXQUEUE_CONFIG
title: _NET_TXQUEUE_CONFIG
author: windows-driver-content
description: Describes the configuration options for a NetAdapterCx client driver's transmit queue.
ms.assetid: a6db5941-763d-4c14-9ba9-86004cc4c56b
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_TXQUEUE_CONFIG, NET_TXQUEUE_CONFIG, *PNET_TXQUEUE_CONFIG, 
req.header: nettxqueue.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_TXQUEUE_CONFIG, *PNET_TXQUEUE_CONFIG
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	nettxqueue.h
apiname: 
-	NET_TXQUEUE_CONFIG
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_TXQUEUE_CONFIG structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Describes the configuration options for a NetAdapterCx client driver's transmit queue.

## -struct-fields

### -field Size
The size of this structure, in bytes.
 
### -field EvtTxQueueCancel
A pointer to the client driver's *[EVT_TXQUEUE_CANCEL](nc-nettxqueue-evt_txqueue_cancel.md)* event callback function. This callback function is required.
 
### -field EvtTxQueueSetNotificationEnabled
A pointer to the client driver's *[EVT_TXQUEUE_SET_NOTIFICATION_ENABLED](nc-nettxqueue-evt_txqueue_set_notification_enabled.md)* event callback function. This callback function is required.
 
### -field EvtTxQueueAdvance
A pointer to the client driver's *[EVT_TXQUEUE_ADVANCE](nc-nettxqueue-evt_txqueue_advance.md)* event callback function. This callback function is required.
 
### -field RingBufferNumberOfElementsHint
A hint at the number of elements for the ring buffer. Set this member if the client driver requires a minimum size for the buffer. If this member is set to **0**, NetAdapterCx will set the ring buffer size to the default value.

## -remarks
Call [NET_TXQUEUE_CONFIG_INIT](nf-nettxqueue-net_txqueue_config_init.md) to initialize this structure.

The **NET_TXQUEUE_CONFIG** structure is an input parameter to [NetTxQueueCreate](nf-nettxqueue-nettxqueuecreate.md). The client must use [NET_TXQUEUE_CONFIG_INIT](nf-nettxqueue-net_txqueue_config_init.md) to initialize this structure before calling **NetTxQueueCreate**.

In NetAdapterCx 1.1, the **ContextTypeInfo** member from version 1.0 was replaced with the **RingBufferNumberOfElementsHint** member.

The minimum NetAdapterCx version for **NET_TXQUEUE_CONFIG** is 1.1.

## -see-also