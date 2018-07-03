---
UID: NC:netadapter.EVT_NET_ADAPTER_CREATE_RXQUEUE
title: EVT_NET_ADAPTER_CREATE_RXQUEUE
author: windows-driver-content
description: The client driver's implementation of the EvtNetAdapterCreateRxQueue event callback function that sets up a receive (Rx) queue.
ms.assetid: 30a51b5b-5da7-4cfa-aaff-433c39f90bd0
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
-	EVT_NET_ADAPTER_CREATE_RXQUEUE
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# EVT_NET_ADAPTER_CREATE_RXQUEUE callback function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The client driver's implementation of the *EvtNetAdapterCreateRxQueue* event callback function that sets up a receive (Rx) queue.

## -prototype

```c++
//Declaration

EVT_NET_ADAPTER_CREATE_RXQUEUE EvtNetAdapterCreateRxqueue; 

// Definition

NTSTATUS EvtNetAdapterCreateRxqueue 
(
	_In_    NETADAPTER          Adapter,
	_Inout_ PNETRXQUEUE_INIT    RxQueueInit
)
{...}

typedef EVT_NET_ADAPTER_CREATE_RXQUEUE *PFN_NET_ADAPTER_CREATE_RXQUEUE;
```

## -parameters

### -param Adapter 
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param RxQueueInit 
A pointer to a NetAdapterCx-allocated **NETRXQUEUE_INIT** structure. For more information, see the Remarks section.


## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate [NTSTATUS](https://msdn.microsoft.com/library/windows/hardware/ff557697) error code.

## -remarks

To register an EVT_NET_ADAPTER_CREATE_RXQUEUE callback function, the client driver must call [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

The **NETRXQUEUE_INIT** structure is an opaque structure that is defined and allocated by NetAdapterCx, similar to [WDFDEVICE_INIT](https://msdn.microsoft.com/library/windows/hardware/ff546951).

In this callback, the client driver might call [NetRxQueueInitGetQueueId](../netrxqueue/nf-netrxqueue-netrxqueueinitgetqueueid.md) to retrieve the identifier of the receive queue to set up.

Next, the client calls [NetRxQueueCreate](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) to allocate a queue. If [NetRxQueueCreate](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) fails, the *EvtNetAdapterCreateRxQueue* callback function should return an error code.

To retrieve the ring buffer associated with a given queue, call [NetRxQueueGetDatapathDescriptor](../netrxqueue/nf-netrxqueue-netrxqueuegetdatapathdescriptor.md), then use the [NET_DATAPATH_DESCRIPTOR](../netdatapathdescriptor/ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure returned by that method to call [NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER](../netdatapathdescriptor/nf-netdatapathdescriptor-net_datapath_descriptor_get_packet_ring_buffer.md).


### Example
NetAdapterCx calls *EvtNetAdapterCreateRxQueue* at the very end of the [power-up sequence](https://docs.microsoft.com/windows-hardware/drivers/netcx/power-up-sequence-for-a-netadaptercx-client-driver). During this callback, client drivers can add packet context attributes to the queue and query for packet extension offsets.

To configure additional properties for its Rx queues, such as DMA or receive buffer allocation requirements, the client driver sets its Rx capabilities in the optional *[EvtNetAdapterSetCapabilities](nc-netadapter-evt_net_adapter_set_capabilities.md)* callback function that is called earlier in the power-up sequence before D0 entry.

Error handling code has been left out of this example for clarity.

```c++
NTSTATUS
EvtAdapterCreateRxQueue(
    _In_ NETADAPTER netAdapter,
    _Inout_ PNETRXQUEUE_INIT rxQueueInit)
{
    NTSTATUS status = STATUS_SUCCESS;

    // Prepare the configuration structure
    NET_RXQUEUE_CONFIG rxConfig;
    NET_RXQUEUE_CONFIG_INIT(
        &rxConfig,
        EvtRxQueueAdvance,
        EvtRxQueueSetNotificationEnabled,
        EvtRxQueueCancel);

    // Initialize the per-packet context
    NET_PACKET_CONTEXT_ATTRIBUTES myRxContextAttributes;
    NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE(&myRxContextAttributes, MY_RXQUEUE_PACKET_CONTEXT);

    // Add the context attributes to the queue
    status = NetRxQueueInitAddPacketContextAttributes(rxQueueInit, &myRxContextAttributes);

    // Get the queue ID
    const ULONG queueId = NetRxQueueInitGetQueueId(rxQueueInit);

    // Create the receive queue
    NETRXQUEUE rxQueue;
    status = NetRxQueueCreate(
        rxQueueInit,
        &rxAttributes,
        &rxConfig,
        &rxQueue);

    // Get the queue context for storing the queue ID and packet extension offset info
    PMY_RX_QUEUE_CONTEXT queueContext = GetMyRxQueueContext(rxQueue);

    // Store the queue ID in the context
    queueContext->QueueId = queueId;

    // Query the checksum packet extension offset and store it in the context
    NET_PACKET_EXTENSION_QUERY extension;
    NET_PACKET_EXTENSION_QUERY_INIT(
        &extension,
        NET_PACKET_EXTENSION_CHECKSUM_NAME,
        NET_PACKET_EXTENSION_CHECKSUM_VERSION_1); 
          
    queueContext->ChecksumExtensionOffset = NetRxQueueGetPacketExtensionOffset(rxQueue, &extension);

    return status;
```

For more information about packet extensions and available packet extension constants, see [Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions).

## -see-also
