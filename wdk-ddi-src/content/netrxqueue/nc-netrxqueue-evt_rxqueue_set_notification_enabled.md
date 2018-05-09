---
UID: NC:netrxqueue.EVT_RXQUEUE_SET_NOTIFICATION_ENABLED
title: EVT_RXQUEUE_SET_NOTIFICATION_ENABLED
author: windows-driver-content
description: Implemented by the client driver to enable receive queue notification for the associated device.
ms.assetid: 82d20c44-ce96-47c5-8d76-6f55b9f42dbb
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netrxqueue.h
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
-	netrxqueue.h
apiname: 
-	EVT_RXQUEUE_SET_NOTIFICATION_ENABLED
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# EVT_RXQUEUE_SET_NOTIFICATION_ENABLED callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Implemented by the client driver to enable receive queue notification for the associated device.

## -prototype

```c++
//Declaration

EVT_RXQUEUE_SET_NOTIFICATION_ENABLED EvtRxqueueSetNotificationEnabled; 

// Definition

VOID EvtRxqueueSetNotificationEnabled 
(
	_In_	NETRXQUEUE	RxQueue,
	_In_	BOOLEAN		NotificationEnabled
)
{...}

typedef EVT_RXQUEUE_SET_NOTIFICATION_ENABLED *PFN_RXQUEUE_SET_NOTIFICATION_ENABLED;
```

## -parameters

### -param RxQueue 
A handle to a net receive queue.

### -param NotificationEnabled 
A value of TRUE requests that the client enable receive queue notification. A value of FALSE requests that the client disable receive queue notification.

## -returns

This callback function does not return a value.

## -remarks
Register this callback function in by setting the appropriate member of [NET_RX_QUEUE_CONFIG](ns-netrxqueue-_net_rxqueue_config.md), initializing the **NET_RX_QUEUE_CONFIG** structure with [NET_RXQUEUE_CONFIG_INIT](nf-netrxqueue-net_rxqueue_config_init.md), then calling [NetRxQueueCreate](nf-netrxqueue-netrxqueuecreate.md).

NetAdapterCx serializes this callback function along with the receive queue's *[EVT_RXQUEUE_ADVANCE](nc-netrxqueue-evt_rxqueue_advance.md)* and *[EVT_RXQUEUE_CANCEL](nc-netrxqueue-evt_rxqueue_cancel.md)* callback functions.

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

The minimum NetAdapterCx version for *EVT_RXQUEUE_SET_NOTIFICATION_ENABLED* is 1.1.

### Example

For a PCI NIC, enabling receive queue notification typically means enabling the receive queue's hardware interrupt. When the hardware interrupt fires, the client calls [NetRxQueueNotifyMoreReceivedPacketsAvailable](nf-netrxqueue-netrxqueuenotifymorereceivedpacketsavailable.md) from its DPC.

For example:

```c++
VOID
EvtRxQueueSetNotificationEnabled(
    _In_ NETRXQUEUE rxQueue,
    _In_ BOOLEAN notificationEnabled)
{
    // optional: retrieve queue's WDF context
    MY_RX_QUEUE_CONTEXT *rxContext = GetRxQueueContext(RxQueue);

    // If notificationEnabled is TRUE, enable receive queue's hardware interrupt
    ...
}

void
EvtInterruptDpc(
    _In_ WDFINTERRUPT interrupt,
    _In_ WDFOBJECT associatedObject)
{
    MY_INTERRUPT_CONTEXT *interruptContext = GetInterruptContext(interrupt);

    NetRxQueueNotifyMoreReceivedPacketsAvailable(interruptContext->RxQueue);
}
```

For a USB device, or any other queue with a software receive completion mechanism, the client driver should track in its own context whether the queue's notification is enabled. From the completion routine (triggered for example when a message becomes available in the USB continuous reader), call [NetRxQueueNotifyMoreReceivedPacketsAvailable](nf-netrxqueue-netrxqueuenotifymorereceivedpacketsavailable.md) if the notification is enabled. The following example shows how you might do this.

```c++
VOID
UsbEvtReaderCompletionRoutine(
    _In_ WDFUSBPIPE pipe,
    _In_ WDFMEMORY buffer,
    _In_ size_t numBytesTransferred,
    _In_ WDFCONTEXT context)
{
    UNREFERENCED_PARAMETER(pipe);

    PUSB_RCB_POOL pRcbPool = *((PUSB_RCB_POOL*) context);
    PUSB_RCB pRcb = (PUSB_RCB) WdfMemoryGetBuffer(buffer, NULL);

    pRcb->DataOffsetCurrent = 0;
    pRcb->DataWdfMemory = buffer;
    pRcb->DataValidSize = numBytesTransferred;

    WdfObjectReference(pRcb->DataWdfMemory);

    ExInterlockedInsertTailList(&pRcbPool->ListHead,
                                &pRcb->Link,
                                &pRcbPool->ListSpinLock);

    if (InterlockedExchange(&pRcbPool->NotificationEnabled, FALSE) == TRUE)
    {
        NetRxQueueNotifyMoreReceivedPacketsAvailable(pRcbPool->RxQueue);
    }

}
```

## -see-also

*[EVT_RXQUEUE_ADVANCE](nc-netrxqueue-evt_rxqueue_advance.md)*

[NetRxQueueNotifyMoreReceivedPacketsAvailable](nf-netrxqueue-netrxqueuenotifymorereceivedpacketsavailable.md)