---
UID: NC:netadapter.EVT_NET_ADAPTER_CREATE_TXQUEUE
title: EVT_NET_ADAPTER_CREATE_TXQUEUE
author: windows-driver-content
description: The client driver's implementation of the EVT_NET_ADAPTER_CREATE_TXQUEUE event callback function that sets up a transmit queue.
ms.assetid: 50d681dc-8d45-45d4-aef6-149ee53c1284
ms.author: windowsdriverdev
ms.date: 02/05/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	netadapter.h
apiname: 
-	EVT_NET_ADAPTER_CREATE_TXQUEUE
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# EVT_NET_ADAPTER_CREATE_TXQUEUE callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The client driver's implementation of the **EVT_NET_ADAPTER_CREATE_TXQUEUE** event callback function that sets up a transmit queue.

## -prototype

```c++
//Declaration

EVT_NET_ADAPTER_CREATE_TXQUEUE EvtNetAdapterCreateTxqueue; 

// Definition

NTSTATUS EvtNetAdapterCreateTxqueue 
(
	_In_    NETADAPTER          Adapter,
	_Inout_ PNETTXQUEUE_INIT    TxQueueInit
)
{...}

typedef EVT_NET_ADAPTER_CREATE_TXQUEUE *PFN_NET_ADAPTER_CREATE_TXQUEUE;
```

## -parameters

### -param Adapter: 
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param TxQueueInit: 
A pointer to a NetAdapterCx-allocated **NETTXQUEUE_INIT** structure. For more information, see the Remarks section.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate [NTSTATUS](https://msdn.microsoft.com/library/windows/hardware/ff557697) error code.

## -remarks

To register an EVT_NET_ADAPTER_CREATE_TXQUEUE callback function, the client driver must call [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

The **NETTXQUEUE_INIT** structure is an opaque structure that is defined and allocated by NetAdapterCx, similar to [WDFDEVICE_INIT](https://msdn.microsoft.com/library/windows/hardware/ff546951).

In this callback, the client driver might call [NetTxQueueInitGetQueueId](../nettxqueue/nf-nettxqueue-nettxqueueinitgetqueueid.md) to retrieve the identifier of the receive queue to set up.

Next, the client calls [NetTxQueueCreate](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md) to allocate a queue. If [NetTxQueueCreate](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md) fails, the *EVT_NET_ADAPTER_CREATE_TXQUEUE* callback function should return an error code.

To retrieve the ring buffer associated with a given queue, call [NetTxQueueGetRingBuffer](../nettxqueue/nf-nettxqueue-nettxqueuegetringbuffer.md).

The minimum NetAdapterCx version for **EVT_NET_ADAPTER_CREATE_TXQUEUE** is 1.0.

## Example

> [!TIP]
> This example transmit queue uses two driver-defined packet contexts - one called MY_TX_PACKET_CONTEXT, and a second called MY_TCB to assist with transmit operations. For more info about setting up this second example packet context and initializing it, see [NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE](../netadapterpacket/nf-netadapterpacket-net_packet_context_attributes_init_type.md).
> 
> Error handling code has been excised from this example for brevity and clarity.

```c++
NTSTATUS
EvtAdapterCreateTxQueue(
    _In_ NETADAPTER netAdapter,
    _Inout_ PNETTXQUEUE_INIT txQueueInit)
{
    NTSTATUS status = STATUS_SUCCESS;

    NET_TXQUEUE_CONFIG txConfig;
    NET_TXQUEUE_CONFIG_INIT(
        &txConfig,
        EvtTxQueueAdvance,
        EvtTxQueueSetNotificationEnabled,
        EvtTxQueueCancel);

    // Initialize the first default packet context

    NET_PACKET_CONTEXT_ATTRIBUTES myTxContextAttributes;
    NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE(&myTxContextAttributes, MY_DEFAULT_TX_PACKET_CONTEXT);

    // Add the first default packet context attributes to the queue

    status = NetTxQueueInitAddPacketContextAttributes(txQueueInit, &myTxContextAttributes);

    // Initialize a second custom packet context for a transmit control block

    NET_PACKET_CONTEXT_ATTRIBUTES tcbContextAttributes;
    NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE(&tcbContextAttributes, MY_TCB);

    // Add the second TCB packet context attributes to the queue

    status = NetTxQueueInitAddPacketContextAttributes(txQueueInit, &tcbContextAttributes);

    // Create the transmit queue

    status = NetTxQueueCreate(
        txQueueInit,
        &txAttributes,
        &txConfig,
        &netAdapter->TxQueue);

    return status;
}
```

## -see-also