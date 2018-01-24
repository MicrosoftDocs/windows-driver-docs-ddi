---
UID: NC:netadapter.EVT_NET_ADAPTER_CREATE_RXQUEUE
title: EVT_NET_ADAPTER_CREATE_RXQUEUE
author: windows-driver-content
description: The client driver's implementation of the EVT_NET_ADAPTER_CREATE_RXQUEUE event callback function that sets up a receive queue.
ms.assetid: 30a51b5b-5da7-4cfa-aaff-433c39f90bd0
ms.author: windowsdriverdev
ms.date: 10/17/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
req.include-header:
req.target-type:
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
---

# EVT_NET_ADAPTER_CREATE_RXQUEUE callback function

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1709.

## -description

The client driver's implementation of the EVT_NET_ADAPTER_CREATE_RXQUEUE event callback function that sets up a receive queue.

## -prototype

```
//Declaration

EVT_NET_ADAPTER_CREATE_RXQUEUE EvtNetAdapterCreateRxqueue; 

// Definition

NTSTATUS EvtNetAdapterCreateRxqueue 
(
	NETADAPTER Adapter
	PNETRXQUEUE_INIT RxQueueInit
)
{...}

EVT_NET_ADAPTER_CREATE_RXQUEUE *PFN_NET_ADAPTER_CREATE_RXQUEUE


```

## -parameters

### -param Adapter: 
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param RxQueueInit: 
A pointer to a NetAdapterCx-allocated **NETRXQUEUE_INIT** structure. For more information, see the Remarks section.


## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate [NTSTATUS](https://msdn.microsoft.com/library/windows/hardware/ff557697) error code.

## -remarks

To register an EVT_NET_ADAPTER_CREATE_RXQUEUE callback function, the client driver must call [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

The **NETRXQUEUE_INIT** structure is an opaque structure that is defined and allocated by NetAdapterCx, similar to [WDFDEVICE_INIT](https://msdn.microsoft.com/library/windows/hardware/ff546951).

In this callback, the client driver might call [NetRxQueueInitGetQueueId](../netrxqueue/nf-netrxqueue-netrxqueueinitgetqueueid.md) to retrieve the identifier of the receive queue to set up.

Next, the client calls [NetRxQueueCreate](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) to allocate a queue. If the client provides a non-zero value in the **AllocationSize** member of the [NET_RXQUEUE_CONFIG](../netrxqueue/ns-netrxqueue-_net_rxqueue_config.md) structure, [NetRxQueueCreate](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) allocates the receive buffers. The client should not use the buffers until after [NetRxQueueCreate](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) has returned. If [NetRxQueueCreate](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) fails, the *EVT_NET_ADAPTER_CREATE_RXQUEUE* callback function should return an error code.

To retrieve the ring buffer associated with a given queue, call [NetRxQueueGetRingBuffer](../netrxqueue/nf-netrxqueue-netrxqueuegetringbuffer.md).

## Example

> [!TIP]
> This example uses DMA allocation for the receive queue. It is assumed that the example code previously declared a context for its NETADAPTER object and included a WDFDMAENABLER object in the context, which will now be retrieved in **EvtAdapterCreateRxQueue** to be used for receive buffer DMA allocation. For more info about receive queue DMA allocation, see [NetRxQueueInitSetDmaAllocatorConfig](../netrxqueue/nf-netrxqueue-netrxqueueinitsetdmaallocatorconfig.md).
>
> Error handling code has been excised from this example for brevity and clarity.

```cpp
NTSTATUS
EvtAdapterCreateRxQueue(
    _In_ NETADAPTER netAdapter,
    _Inout_ PNETRXQUEUE_INIT rxQueueInit)
{
    NTSTATUS status = STATUS_SUCCESS;

    NET_RXQUEUE_CONFIG rxConfig;
    NET_RXQUEUE_CONFIG_INIT(
        &rxConfig,
        EvtRxQueueAdvance,
        EvtRxQueueSetNotificationEnabled,
        EvtRxQueueCancel);

    // Specify buffer size required per packet so the OS can preallocate

    rxConfig.AlignmentRequirement = 64;
    rxConfig.AllocationSize = NIC_MAX_PACKET_SIZE + FRAME_CRC_SIZE + RSVD_BUF_SIZE;

    // Initialize the per-packet context

    NET_PACKET_CONTEXT_ATTRIBUTES myRxContextAttributes;
    NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE(&myRxContextAttributes, MY_RXQUEUE_PACKET_CONTEXT);

    // Add the context attributes to the queue

    status = NetRxQueueInitAddPacketContextAttributes(rxQueueInit, &myRxContextAttributes);

    // Retrieve the WDFDMAENABLER from the NETADAPTER's context to opt in to DMA allocation

    MY_NET_ADAPTER_CONTEXT *adapterContext = GetMyNetAdapterContext(netAdapter);
    WDFDMAENABLER dmaEnabler = adapterContext->dmaEnabler;

    // Specify that the OS use the WDFDMAENABLER to allocate the receive buffers

    NET_RXQUEUE_DMA_ALLOCATOR_CONFIG dmaAllocatorConfig;
    NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT(
        &dmaAllocatorConfig,
        dmaEnabler);

    NetRxQueueInitSetDmaAllocatorConfig(
        &rxQueueInit,
        &dmaAllocatorConfig);

    // Create the receive queue

    status = NetRxQueueCreate(
        rxQueueInit,
        &rxAttributes,
        &rxConfig,
        &netAdapter->RxQueue);

     return status;
```

The minimum NetAdapterCx version for EVT_NET_ADAPTER_CREATE_RXQUEUE is 1.0.

## -see-also