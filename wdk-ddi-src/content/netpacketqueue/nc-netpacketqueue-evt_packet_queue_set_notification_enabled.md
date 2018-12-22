---
UID: NC:netpacketqueue.EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED
title: EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED
description: The EvtPacketQueueSetNotificationEnabled callback function is implemented by the client driver to perform client-specific processing when there are new packets received in the specified queue's ring buffer.
tech.root: netvista
ms.assetid: 1a1adb5b-3953-44d5-8d82-aeb210a20c30
ms.date: 07/16/2018
ms.topic: callback
req.header: netpacketqueue.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	netpacketqueue.h
api_name: 
-	EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EvtPacketQueueSetNotificationEnabled* callback function is implemented by the client driver to perform client-specific processing when there are new packets received in the specified queue's ring buffer.

## -prototype

```C++
//Declaration

EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED EvtPacketQueueSetNotificationEnabled; 

// Definition

VOID EvtPacketQueueSetNotificationEnabled 
(
	NETPACKETQUEUE PacketQueue
	BOOLEAN NotificationEnabled
)
{...}

```

## -parameters

### -param PacketQueue

A handle to a packet queue.

### -param NotificationEnabled

A value of **TRUE** requests that the client enable packet queue notification. A value of **FALSE** requests that the client disable packet queue notification.

## -returns

This callback function does not return a value.

## -remarks

This callback indicates to a client driver that polling (of [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) or [*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md)) will stop and will not continue until the client driver calls [**NetTxQueueNotifyMoreCompletedPacketsAvailable**](../nettxqueue/nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md) or [**NetRxQueueNotifyMoreReceivedPacketsAvailable**](../netrxqueue/nf-netrxqueue-netrxqueuenotifymorereceivedpacketsavailable.md). Typically, a PCI device uses this callback to enable Tx or Rx interrupts. Once an interrupt is received, interrupts can be disabled again and the client driver calls **NetTxQueueNotifyMoreCompletedPacketsAvailable** or **NetRxQueueNotifyMoreReceivedPacketsAvailable** to trigger the framework to begin polling again.

Register this callback function in your *EVT_NET_ADAPTER_CREATE_TX(RX)QUEUE* callback. Set the appropriate member of a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure when you are initializing the structure with [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md), then call **NetTx(Rx)QueueCreate**.

NetAdapterCx serializes this callback function along with the packet queue's [*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md) and [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) callback functions.

For more info and a diagram showing the NetAdapterCx data path polling model, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues).

### Transmit queue example

For a PCI NIC, enabling transmit queue notification typically means enabling the transmit queue's hardware interrupt. When the hardware interrupt fires, the client calls [**NetTxQueueNotifyMoreCompletedPacketsAvailable**](../nettxqueue/nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md) from its DPC.

Similarly, for a PCI NIC, disabling queue notification means disabling the interrupt associated with the queue.

For a device that has an asynchronous I/O model, the client typically uses an internal flag to track the enabled state. When an asynchronous operation completes, the completion handler checks this flag and calls [**NetTxQueueNotifyMoreCompletedPacketsAvailable**](../nettxqueue/nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md) if it is set.

If NetAdapterCx calls *EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED* with *NotificationEnabled* set to **FALSE**, the client must not call [**NetTxQueueNotifyMoreCompletedPacketsAvailable**](../nettxqueue/nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md) until NetAdapterCx next calls this callback function with *NotificationEnabled* set to **TRUE**.

For example:

```C++
VOID
MyEvtTxQueueSetNotificationEnabled(
    _In_ NETPACKETQUEUE TxQueue,
    _In_ BOOLEAN NotificationEnabled)
{
    // optional: retrieve queue's WDF context
    MY_TX_QUEUE_CONTEXT *txContext = GetTxQueueContext(TxQueue);

    // If NotificationEnabled is TRUE, enable transmit queue's hardware interrupt
    ...
}

VOID
MyEvtTxInterruptDpc(
    _In_ WDFINTERRUPT Interrupt,
    _In_ WDFOBJECT AssociatedObject)
{
    MY_INTERRUPT_CONTEXT *interruptContext = GetInterruptContext(Interrupt);

    NetTxQueueNotifyMoreCompletedPacketsAvailable(interruptContext->TxQueue);
}
```

### Receive queue example

For a PCI NIC, enabling receive queue notification typically means enabling the receive queue's hardware interrupt. When the hardware interrupt fires, the client calls [**NetRxQueueNotifyMoreReceivedPacketsAvailable**](../netrxqueue/nf-netrxqueue-netrxqueuenotifymorereceivedpacketsavailable.md) from its DPC.

For example:

```C++
VOID
MyEvtRxQueueSetNotificationEnabled(
    _In_ NETRXQUEUE RxQueue,
    _In_ BOOLEAN NotificationEnabled)
{
    // optional: retrieve queue's WDF Context
    MY_RX_QUEUE_CONTEXT *rxContext = GetRxQueueContext(RxQueue);

    // If NotificationEnabled is TRUE, enable receive queue's hardware interrupt
    ...
}

VOID
MyEvtRxInterruptDpc(
    _In_ WDFINTERRUPT Interrupt,
    _In_ WDFOBJECT AssociatedObject)
{
    MY_INTERRUPT_CONTEXT *interruptContext = GetInterruptContext(Interrupt);

    NetRxQueueNotifyMoreReceivedPacketsAvailable(interruptContext->RxQueue);
}
```

For a USB device, or any other queue with a software receive completion mechanism, the client driver should track in its own Context whether the queue's notification is enabled. From the completion routine (triggered for example when a message becomes available in the USB continuous reader), call [**NetRxQueueNotifyMoreReceivedPacketsAvailable**](../netrxqueue/nf-netrxqueue-netrxqueuenotifymorereceivedpacketsavailable.md) if the notification is enabled. The following example shows how you might do this.

```C++
VOID
UsbEvtReaderCompletionRoutine(
    _In_ WDFUSBPIPE Pipe,
    _In_ WDFMEMORY Buffer,
    _In_ size_t NumBytesTransferred,
    _In_ WDFCONTEXT Context)
{
    UNREFERENCED_PARAMETER(Pipe);

    PUSB_RCB_POOL pRcbPool = *((PUSB_RCB_POOL*) Context);
    PUSB_RCB pRcb = (PUSB_RCB) WdfMemoryGetBuffer(Buffer, NULL);

    pRcb->DataOffsetCurrent = 0;
    pRcb->DataWdfMemory = Buffer;
    pRcb->DataValidSize = NumBytesTransferred;

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

[*EVT_NET_ADAPTER_CREATE_RXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)

[*EVT_NET_ADAPTER_CREATE_TXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[*EVT_PACKET_QUEUE_START*](nc-netpacketqueue-evt_packet_queue_start.md)

[*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md)

[*EVT_PACKET_QUEUE_STOP*](nc-netpacketqueue-evt_packet_queue_stop.md)

[**NetTxQueueNotifyMoreCompletedPacketsAvailable**](../nettxqueue/nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md)

[**NetRxQueueNotifyMoreReceivedPacketsAvailable**](../netrxqueue/nf-netrxqueue-netrxqueuenotifymorereceivedpacketsavailable.md)
