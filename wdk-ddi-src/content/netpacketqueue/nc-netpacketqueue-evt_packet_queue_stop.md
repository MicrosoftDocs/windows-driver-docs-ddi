---
UID: NC:netpacketqueue.EVT_PACKET_QUEUE_STOP
title: EVT_PACKET_QUEUE_STOP
author: windows-driver-content
description: The EvtPacketQueueStop callback function is implemented by the client driver to stop the data path for a packet queue before it is deleted.
ms.assetid: 42ae223c-fe68-48ff-b086-92d8a406d4b6
ms.author: windowsdriverdev
ms.date: 07/18/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	EVT_PACKET_QUEUE_STOP
product: Windows
targetos: Windows
---

# EVT_PACKET_QUEUE_STOP callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EvtPacketQueueStop* callback function is implemented by the client driver to stop the data path for a packet queue before it is deleted.

## -prototype

```C++
//Declaration

EVT_PACKET_QUEUE_STOP EvtPacketQueueStop; 

// Definition

VOID EvtPacketQueueStop 
(
	NETPACKETQUEUE PacketQueue
)
{...}

```

## -parameters

### -param PacketQueue

A handle to a packet queue.

## -returns

This callback function does not return a value.

## -remarks

Register this callback function in your *EVT_NET_ADAPTER_CREATE_TX(rxQueueContext)QUEUE* callback. Set the appropriate member of a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure after you initialize the structure with [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md), then call **NetTx(rxQueueContext)QueueCreate**.

For more info and a diagram showing the NetAdapterCx data path polling model, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

### Transmit queue example

When stopping the data path for a transmit queue, client drivers typically clear information they previously set in [*EvtPacketQueueStart*](nc-netpacketqueue-evt_packet_queue_start.md) and disable their hardware interrupt.

```C++
VOID
MyEvtTxQueueStop(
    NETPACKETQUEUE TxQueue
)
{
    PMY_TX_QUEUE_CONTEXT *txQueueContext = MyGetTxQueueContext(TxQueue);

    WdfSpinLockAcquire(txQueueContext->Adapter->Lock);

	// Clear the control/status register's command register
    txQueueContext->Adapter->CSRAddress->CmdReg &= ~CR_TE;

	// Disable the hardware interrupt
    MyTxQueueSetInterrupt(txQueueContext, 
						  false);

	// Clear the handle to the queue
    txQueueContext->Adapter->TxQueue = WDF_NO_HANDLE;

    WdfSpinLockRelease(txQueueContext->Adapter->Lock);
}
```

### Receive queue example

The pattern for stopping a receive queue is typically similar to stopping a transmit queue. This example takes into account multiple receive queues.

```C++
VOID
MyEvtRxQueueStop(
    NETPACKETQUEUE RxQueue
)
{
    PMY_RX_QUEUE_CONTEXT *rxQueueContext = RtGetRxQueueContext(RxQueue);

    WdfSpinLockAcquire(rxQueueContext->Adapter->Lock);

	// Iterate through all of this adapter's receive queues
    bool count = 0;
    for (size_t i = 0; i < ARRAYSIZE(rxQueueContext->Adapter->RxQueues); i++)
    {
        if (rxQueueContext->Adapter->RxQueues[i])
        {
            count++;
        }
    }

	// Clear the control/status register's command register only if this is the last receive queue
    if (1 == count)
    {
        rxQueueContext->Adapter->CSRAddress->CmdReg &= ~CR_RE;
    }

	// Disable the hardware interrupt
    MyRxQueueSetInterrupt(rxQueueContext, 
						  false);

	// Clear the handle to the queue
    rxQueueContext->Adapter->RxQueues[rxQueueContext->QueueId] = WDF_NO_HANDLE;

    WdfSpinLockRelease(rxQueueContext->Adapter->Lock);
}
```

## -see-also

[*EVT_NET_ADAPTER_CREATE_RXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)

[*EVT_NET_ADAPTER_CREATE_TXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[*EVT_PACKET_QUEUE_START*](nc-netpacketqueue-evt_packet_queue_start.md)

[*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)

[*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md)
