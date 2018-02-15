---
UID: NC:nettxqueue.EVT_TXQUEUE_CANCEL
title: EVT_TXQUEUE_CANCEL
author: windows-driver-content
description: Implemented by the client driver to handle operations that must be performed before a transmit queue is deleted.
ms.assetid: 69052561-781e-4fc8-b706-a5ba644236df
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	UserDefined
apilocation: 
-	nettxqueue.h
apiname: 
-	EVT_TXQUEUE_CANCEL
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# EVT_TXQUEUE_CANCEL callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Implemented by the client driver to handle operations that must be performed before a transmit queue is deleted.

## -prototype

```c++
//Declaration

EVT_TXQUEUE_CANCEL EvtTxqueueCancel; 

// Definition

VOID EvtTxqueueCancel 
(
	_In_	NETTXQUEUE	TxQueue
)
{...}

typedef EVT_TXQUEUE_CANCEL *PFN_TXQUEUE_CANCEL;
```

## -parameters

### -param TxQueue: 
A handle to a net transmit queue.

## -returns

This callback function does not return a value.

## -remarks
Register this callback function in by setting the appropriate member of [NET_TX_QUEUE_CONFIG](ns-nettxqueue-_net_txqueue_config.md), initializing the **NET_TX_QUEUE_CONFIG** structure with [NET_TXQUEUE_CONFIG_INIT](nf-nettxqueue-net_txqueue_config_init.md), then calling [NetRxQueueCreate](nf-nettxqueue-nettxqueuecreate.md).

In its *EVT_TXQUEUE_CANCEL* callback function, the client has an opportunity to complete any outstanding transmit packets. Unlike with *[EVT_RXQUEUE_CANCEL](../netrxqueue/nc-netrxqueue-evt_rxqueue_cancel.md), the client is not required to do so. If the client leaves outstanding packets, NetAdapterCx calls the client's  *[EVT_TXQUEUE_ADVANCE](nc-nettxqueue-evt_txqueue_advance.md)*, where the client processes them as part of its regular operation.

If the hardware supports cancelling in-flight transmits, the client should also advance the ring buffer's **BeginIndex** past all cancelled packets. If the hardware does not support cancellation, this callback can return without taking action.

For more info about ring buffer usage, see *[EVT_TXQUEUE_ADVANCE](nc-nettxqueue-evt_txqueue_advance.md)* and [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

NetAdapterCx serializes this callback function along with the receive queue's *[EVT_TXQUEUE_ADVANCE](nc-nettxqueue-evt_txqueue_advance.md)* and *[EVT_TXQUEUE_SET_NOTIFICATION_ENABLED](nc-nettxqueue-evt_txqueue_set_notification_enabled.md)* callback functions.

The minimum NetAdapterCx version for *EVT_TXQUEUE_CANCEL* is 1.0.

## -see-also