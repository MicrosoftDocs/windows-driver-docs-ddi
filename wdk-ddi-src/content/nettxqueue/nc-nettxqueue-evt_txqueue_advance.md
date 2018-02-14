---
UID: NC:nettxqueue.EVT_TXQUEUE_ADVANCE
title: EVT_TXQUEUE_ADVANCE
author: windows-driver-content
description: Implemented by the client driver to process transmit packets provided by NetAdapterCx.
ms.assetid: a15562c8-5ff1-40dc-9d38-66fa2b7834aa
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
req.irql: <= DISPATCH_LEVEL
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
-	EVT_TXQUEUE_ADVANCE
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# EVT_TXQUEUE_ADVANCE callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Implemented by the client driver to process transmit packets provided by NetAdapterCx.

## -prototype

```c++
//Declaration

EVT_TXQUEUE_ADVANCE EvtTxqueueAdvance; 

// Definition

VOID EvtTxqueueAdvance 
(
	_In_	NETTXQUEUE	TxQueue
)
{...}

typedef EVT_TXQUEUE_ADVANCE *PFN_TXQUEUE_ADVANCE;
```

## -parameters

### -param TxQueue: 
A handle to a net transmit queue.

## -returns

This callback function does not return a value.

## Example
In this callback, the client retrieves packets from the queue, programs the hardware to send the data, and returns any completed packets.

To return packets, call [NetRingBufferIncrementIndex](../netringbuffer/nf-netringbuffer-netringbufferincrementindex.md), or use a helper method such as [NetRingBufferReturnCompletedPackets](../netadapterpacket/nf-netadapterpacket-netringbufferreturncompletedpackets.md).

The following example retrieves incoming transmit packets from the queue and immediately completes them.

```c++
VOID
EvtTxQueueAdvance(NETTXQUEUE TxQueue)
{
    NET_RING_BUFFER *ringBuffer = NetTxQueueGetRingBuffer(TxQueue);
    NET_PACKET *netPacket;

    // Retrieve pointer to packet at the NextIndex value of the ring buffer

    while ((netPacket = NetRingBufferGetNextPacket(ringBuffer)) != nullptr)
    {

        // Transmit the data

        netPacket->Data.Completed = TRUE;

        // Increment NextIndex

        NetRingBufferAdvanceNextPacket(ringBuffer);
    }

    NetRingBufferReturnCompletedPackets(ringBuffer);
```

## -remarks
Register this callback function in by setting the appropriate member of [NET_TX_QUEUE_CONFIG](ns-nettxqueue-_net_txqueue_config.md), initializing the **NET_TX_QUEUE_CONFIG** structure with [NET_TXQUEUE_CONFIG_INIT](nf-nettxqueue-net_txqueue_config_init.md), then calling [NetRxQueueCreate](nf-nettxqueue-nettxqueuecreate.md).
	
NetAdapterCx serializes this callback function along with the receive queue's *[EVT_TXQUEUE_CANCEL](nc-nettxqueue-evt_txqueue_cancel.md)* and *[EVT_TXQUEUE_SET_NOTIFICATION_ENABLED](nc-nettxqueue-evt_txqueue_set_notification_enabled.md)* callback functions.

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

The minimum NetAdapterCx version for *EVT_TXQUEUE_ADVANCE* is 1.0.

## -see-also

[NetTxQueueGetRingBuffer](nf-nettxqueue-nettxqueuegetringbuffer.md)