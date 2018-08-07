---
UID: NS:netrxqueue._NET_RXQUEUE_CONFIG
title: _NET_RXQUEUE_CONFIG
author: windows-driver-content
description: Describes the configuration options for a NetAdapterCx client driver's receive queue.
ms.assetid: 84d0ef9e-c23f-4040-9a7f-a373d69b5765
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_RXQUEUE_CONFIG, *PNET_RXQUEUE_CONFIG, NET_RXQUEUE_CONFIG, 
req.header: netrxqueue.h
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
req.typenames: NET_RXQUEUE_CONFIG, *PNET_RXQUEUE_CONFIG
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrxqueue.h
apiname: 
-	NET_RXQUEUE_CONFIG
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_RXQUEUE_CONFIG structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Describes the configuration options for a NetAdapterCx client driver's receive queue.

## -struct-fields

### -field Size
 The size of this structure, in bytes.

### -field EvtRxQueueCancel
A pointer to the client driver's *[EVT_RXQUEUE_CANCEL](nc-netrxqueue-evt_rxqueue_cancel.md)* event callback function. This callback function is required.
 
### -field EvtRxQueueSetNotificationEnabled
A pointer to the client driver's *[EVT_RXQUEUE_SET_NOTIFICATION_ENABLED](nc-netrxqueue-evt_rxqueue_advance.md)* event callback function. This callback function is required.
 
### -field EvtRxQueueAdvance
A pointer to the client driver's *[EVT_RXQUEUE_ADVANCE](nc-netrxqueue-evt_rxqueue_advance.md)* event callback function. This callback function is required.

## -remarks
Call [NET_RXQUEUE_CONFIG_INIT](nf-netrxqueue-net_rxqueue_config_init.md) to initialize this structure.

The **NET_RXQUEUE_CONFIG** structure is an input parameter to [NetRxQueueCreate](nf-netrxqueue-netrxqueuecreate.md). The client must use [NET_RXQUEUE_CONFIG_INIT](nf-netrxqueue-net_rxqueue_config_init.md) to initialize this structure before calling **NetRxQueueCreate**.



## -see-also