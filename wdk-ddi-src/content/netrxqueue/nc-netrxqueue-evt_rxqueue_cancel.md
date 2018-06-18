---
UID: NC:netrxqueue.EVT_RXQUEUE_CANCEL
title: EVT_RXQUEUE_CANCEL
author: windows-driver-content
description: Implemented by the client driver to handle operations that must be performed before a receive queue is deleted.
ms.assetid: 544afa55-ba29-4118-84a3-0827cbe2cc66
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
-	netrxqueue.h
apiname: 
-	EVT_RXQUEUE_CANCEL
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# EVT_RXQUEUE_CANCEL callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Implemented by the client driver to handle operations that must be performed before a receive queue is deleted.

## -prototype

```c++
//Declaration

EVT_RXQUEUE_CANCEL EvtRxqueueCancel; 

// Definition

VOID EvtRxqueueCancel 
(
	_In_	NETRXQUEUE	RxQueue
)
{...}

typedef EVT_RXQUEUE_CANCEL *PFN_RXQUEUE_CANCEL;
```

## -parameters

### -param RxQueue 
A handle to a net receive queue.

## -returns

This callback function does not return a value.

## -remarks
Register this callback function in by setting the appropriate member of [NET_RX_QUEUE_CONFIG](ns-netrxqueue-_net_rxqueue_config.md), initializing the **NET_RX_QUEUE_CONFIG** structure with [NET_RXQUEUE_CONFIG_INIT](nf-netrxqueue-net_rxqueue_config_init.md), then calling [NetRxQueueCreate](nf-netrxqueue-netrxqueuecreate.md).

NetAdapterCx serializes this callback function along with the receive queue's *[EVT_RXQUEUE_ADVANCE](nc-netrxqueue-evt_rxqueue_advance.md)* and *[EVT_RXQUEUE_SET_NOTIFICATION_ENABLED](nc-netrxqueue-evt_rxqueue_set_notification_enabled.md)* callback functions.

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).



### Example

In your *EVT_RXQUEUE_CANCEL* callback function, you must complete any outstanding receive packets. If you do not return all packets, the operating system does not delete the queue, and NetAdapterCx stops calling your callbacks for the queue. To return packets, call the [NetRingBufferReturnAllPackets](../netadapterpacket/nf-netadapterpacket-netringbufferreturnallpackets.md) method.

```c++
VOID
EvtRxQueueCancel(NETRXQUEUE RxQueue)
{
    PCNET_DATAPATH_DESCRIPTOR descriptor = NetRxQueueGetDatapathDescriptor(RxQueue);

    NetRingBufferReturnAllPackets(descriptor);
}
```

For additional example code demonstrating ring buffer usage, see *[EVT_RXQUEUE_ADVANCE](nc-netrxqueue-evt_rxqueue_advance.md)*.

## -see-also