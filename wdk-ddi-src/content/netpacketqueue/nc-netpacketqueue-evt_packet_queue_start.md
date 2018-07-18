---
UID: NC:netpacketqueue.EVT_PACKET_QUEUE_START
title: EVT_PACKET_QUEUE_START
author: windows-driver-content
description: The EvtPacketQueueStart callback function is implemented by the client driver to start the data path for a packet queue.
ms.assetid: 0B5CB7F0-C840-4138-8B22-4FE35120C7A5
ms.author: windowsdriverdev
ms.date: 07/17/2018
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
-	EVT_PACKET_QUEUE_START
product: Windows
targetos: Windows
---

# EVT_PACKET_QUEUE_START callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EvtPacketQueueStart* callback function is implemented by the client driver to start the data path for a packet queue after it has been created.

## -prototype

```C++
//Declaration

EVT_PACKET_QUEUE_START EvtPacketQueueStart; 

// Definition

VOID EvtPacketQueueStart 
(
	NETPACKETQUEUE PacketQueue
)
{...}

```

## -parameters

### -param PacketQueue

A handle to a packet queue.

## -returns

This callback does not return a value.

## -remarks

Register this callback function in your *EVT_NET_ADAPTER_CREATE_TX(RX)QUEUE* callback. Set the appropriate member of a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure after you initialize the structure with [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md), then call **NetTx(Rx)QueueCreate**.

For more info and a diagram showing the NetAdapterCx data path polling model, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

### Transmit queue example

In this callback, a client driver typically configures information that that its hardware needs for packet transmission or reception. The following example shows how a client driver might do this for a transmit queue.

```C++
VOID
MyEvtTxQueueStart(
    NETPACKETQUEUE TxQueue
)
{
    PMY_TX_QUEUE_CONTEXT *txQueueContext = MyGetTxQueueContext(TxQueue);
    NETADAPTER *adapter = txQueueContext->Adapter;

    RtlZeroMemory(txQueueContext->TxDescriptorBase, txQueueContext->TransmitSize);

    txQueueContext->TxDescriptorIndex = 0;

    WdfSpinLockAcquire(adapter->Lock);

	// Set the control/status register's transmit descriptor fetch number
    adapter->CSRAddress->TDFNR = 8;

    // Set the max transmit packet size
    adapter->CSRAddress->MtpsReg.MTPS = (RT_MAX_FRAME_SIZE + 128 - 1) / 128;

    PHYSICAL_ADDRESS physicalAddress = WdfCommonBufferGetAlignedLogicalAddress(txQueueContext->TxDescriptorArray);

    // Let the hardware know where transmit descriptors are
    adapter->CSRAddress->TNPDSLow = physicalAddress.LowPart;
    adapter->CSRAddress->TNPDSHigh = physicalAddress.HighPart;

    adapter->CSRAddress->CmdReg |= CR_TE;

    // The transmit control register (TCR) should only be modified after the transceiver is enabled
    adapter->CSRAddress->TCR = (TCR_RCR_MXDMA_UNLIMITED << TCR_MXDMA_OFFSET) | (TCR_IFG0 | TCR_IFG1 | TCR_BIT0);
    adapter->TxQueue = TxQueue;

    WdfSpinLockRelease(adapter->Lock);
}
```

### Receive queue example

Starting a receive queue might be similar to starting a transmit queue, except that the hardware might have multiple receive queues instead of one transmit queue and might have different requirements for updating the control register.

```C++
VOID
MyEvtRxQueueStart(
    NETPACKETQUEUE RxQueue
)
{
    PMY_RX_QUEUE_CONTEXT *rxQueueContext = MyGetRxQueueContext(RxQueue);
    NETADAPTER *adapter = rxQueueContext->Adapter;

    RtlZeroMemory(rxQueueContext->RxdBase, rxQueueContext->RxdSize);

	// Let the hardware know where the receive descriptors are
    PHYSICAL_ADDRESS physicalAddress = WdfCommonBufferGetAlignedLogicalAddress(rxQueueContext->RxDescriptorArray);
    if (rxQueueContext->QueueId == 0)
    {
        adapter->CSRAddress->RDSARLow = physicalAddress.LowPart;
        adapter->CSRAddress->RDSARHigh = physicalAddress.HighPart;
    }
    else
    {
        MySetRxDescriptorStartAddress(adapter, 
									  rxQueueContext->QueueId, 
									  physicalAddress);
    }

    WdfSpinLockAcquire(adapter->Lock);

    if (! (adapter->CSRAddress->CmdReg & CR_RE))
    {
        adapter->CSRAddress->CmdReg |= CR_RE;
    }
    adapter->RxQueues[rxQueueContext->QueueId] = RxQueue;

	// Update the receive control register
    MyAdapterUpdateRcr(adapter);

    WdfSpinLockRelease(adapter->Lock);
}
```

## -see-also

[*EVT_NET_ADAPTER_CREATE_RXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)

[*EVT_NET_ADAPTER_CREATE_TXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)

[*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md)

[*EVT_PACKET_QUEUE_STOP*](nc-netpacketqueue-evt_packet_queue_stop.md)