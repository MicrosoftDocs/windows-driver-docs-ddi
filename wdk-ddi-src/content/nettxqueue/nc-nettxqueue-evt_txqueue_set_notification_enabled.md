---
UID: NC:nettxqueue.EVT_TXQUEUE_SET_NOTIFICATION_ENABLED
title: EVT_TXQUEUE_SET_NOTIFICATION_ENABLED
author: windows-driver-content
description: Implemented by the client driver to perform client-specific processing when there are new packets received in the specified queue's ring buffer.
ms.assetid: c9154f9a-b516-49f3-8402-0221f80b7400
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
req.kmdf-ver: 1.23
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
-	EVT_TXQUEUE_SET_NOTIFICATION_ENABLED
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# EVT_TXQUEUE_SET_NOTIFICATION_ENABLED callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Implemented by the client driver to perform client-specific processing when there are new packets received in the specified queue's ring buffer.

## -prototype

```c++
//Declaration

EVT_TXQUEUE_SET_NOTIFICATION_ENABLED EvtTxqueueSetNotificationEnabled; 

// Definition

VOID EvtTxqueueSetNotificationEnabled 
(
	_In_	NETTXQUEUE	TxQueue,
	_In_	BOOLEAN		NotificationEnabled
)
{...}

typedef EVT_TXQUEUE_SET_NOTIFICATION_ENABLED *PFN_TXQUEUE_SET_NOTIFICATION_ENABLED;
```

## -parameters

### -param TxQueue: 
A handle to a net transmit queue.

### -param NotificationEnabled: 
A value of **TRUE** requests that the client enable transmit queue notification. A value of **FALSE** requests that the client disable transmit queue notification.

## -returns

This callback function does not return a value.

## -remarks
Register this callback function in by setting the appropriate member of [NET_TX_QUEUE_CONFIG](ns-nettxqueue-_net_txqueue_config.md), initializing the **NET_TX_QUEUE_CONFIG** structure with [NET_TXQUEUE_CONFIG_INIT](nf-nettxqueue-net_txqueue_config_init.md), then calling [NetRxQueueCreate](nf-nettxqueue-nettxqueuecreate.md).

NetAdapterCx serializes this callback function along with the receive queue's *[EVT_TXQUEUE_ADVANCE](nc-nettxqueue-evt_txqueue_advance.md)* and *[EVT_TXQUEUE_SET_CANCEL](nc-nettxqueue-evt_txqueue_cancel.md)* callback functions.

In NetAdapterCx 1.1, the return type of this method was changed from **NTSTATUS** in version 1.0 to **VOID**.

The minimum NetAdapterCx version for *EVT_TXQUEUE_SET_NOTIFICATION_ENABLED* is 1.1.

### Example
For a PCI NIC, enabling transmit queue notification typically means enabling the transmit queue's hardware interrupt. When the hardware interrupt fires, the client calls [NetTxQueueNotifyMoreCompletedPacketsAvailable](nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md) from its DPC.

Similarly, for a PCI NIC, disabling queue notification means disabling the interrupt associated with the queue.

For a device that has an asynchronous I/O model, the client typically uses an internal flag to track the enabled state. When an asynchronous operation completes, the completion handler checks this flag and calls [NetTxQueueNotifyMoreCompletedPacketsAvailable](nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md) if it is set.

If NetAdapterCx calls *EVT_TXQUEUE_SET_NOTIFICATION_ENABLED* with *NotificationEnabled* set to **FALSE**, the client must not call [NetTxQueueNotifyMoreCompletedPacketsAvailable](nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md) until NetAdapterCx next calls this callback function with *NotificationEnabled* set to **TRUE**.

For example:

```c++
VOID
EvtTxQueueSetNotificationEnabled(
    _In_ NETTXQUEUE rxQueue,
    _In_ BOOLEAN notificationEnabled)
{
    // optional: retrieve queue's WDF context
    MY_TX_QUEUE_CONTEXT *txContext = GetTxQueueContext(TxQueue);

    // If notificationEnabled is TRUE, enable transmit queue's hardware interrupt
    ...
}

void
EvtInterruptDpc(
    _In_ WDFINTERRUPT interrupt,
    _In_ WDFOBJECT associatedObject)
{
    MY_INTERRUPT_CONTEXT *interruptContext = GetInterruptContext(interrupt);

    NetTxQueueNotifyMoreCompletedPacketsAvailable(interruptContext->TxQueue);
}
```

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

## -see-also

*[EVT_TXQUEUE_ADVANCE](nc-nettxqueue-evt_txqueue_advance.md)*

[NetTxQueueNotifyMoreCompletedPacketsAvailable](nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md)