---
UID: NC:netadapter.EVT_NET_ADAPTER_CREATE_TXQUEUE
title: EVT_NET_ADAPTER_CREATE_TXQUEUE
author: windows-driver-content
description: The client driver's implementation of the *EvtNetAdapterCreateTxQueue* event callback function that sets up a transmit (Tx) queue.
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
product:
-	Windows
targetos: Windows
req.typenames: 
product:
- Windows
---

# EVT_NET_ADAPTER_CREATE_TXQUEUE callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The client driver's implementation of the *EvtNetAdapterCreateTxQueue* event callback function that sets up a transmit (Tx) queue.

## -prototype

```C++
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

### -param Adapter 
The network adapter object that the client created in a prior call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param TxQueueInit 
A pointer to a NetAdapterCx-allocated **NETTXQUEUE_INIT** structure. For more information, see the Remarks section.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate [NTSTATUS](https://msdn.microsoft.com/library/windows/hardware/ff557697) error code.

## -remarks

To register an *EVT_NET_ADAPTER_CREATE_TXQUEUE* callback function, the client driver must call [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

The **NETTXQUEUE_INIT** structure is an opaque structure that is defined and allocated by NetAdapterCx, similar to [WDFDEVICE_INIT](https://msdn.microsoft.com/library/windows/hardware/ff546951).

In this callback, the client driver might call [NetTxQueueInitGetQueueId](../nettxqueue/nf-nettxqueue-nettxqueueinitgetqueueid.md) to retrieve the identifier of the transmit queue to set up.

Next, the client calls [NetTxQueueCreate](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md) to allocate a queue. If [NetTxQueueCreate](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md) fails, the *EvtNetAdapterCreateTxQueue* callback function should return an error code.

To retrieve the ring buffer associated with a given queue, call [**NetTxQueueGetDatapathDescriptor**](../nettxqueue/nf-nettxqueue-nettxqueuegetdatapathdescriptor.md), then use the [**NET_DATAPATH_DESCRIPTOR**](../netdatapathdescriptor/ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure returned by that method to call [**NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER**](../netdatapathdescriptor/nf-netdatapathdescriptor-net_datapath_descriptor_get_packet_ring_buffer.md).

### Example

NetAdapterCx calls *EvtNetAdapterCreateTxQueue* at the very end of the [power-up sequence](https://docs.microsoft.com/windows-hardware/drivers/netcx/power-up-sequence-for-a-netadaptercx-client-driver). During this callback, client drivers can add packet context attributes to the queue and query for packet extension offsets.

Error handling code has been left out of this example for clarity.

```C++
NTSTATUS
EvtAdapterCreateTxQueue(
    _In_ NETADAPTER netAdapter,
    _Inout_ PNETTXQUEUE_INIT txQueueInit
    )
{
    NTSTATUS status = STATUS_SUCCESS;

    // Prepare the configuration structure
    NET_PACKET_QUEUE_CONFIG txConfig;
    NET_PACKET_QUEUE_CONFIG_INIT(
        &txConfig,
        EvtTxQueueAdvance,
        EvtTxQueueSetNotificationEnabled,
        EvtTxQueueCancel);

    // Optional: register the queue's start and stop callbacks
    txConfig.EvtStart = EvtTxQueueStart;
    txConfig.EvtStop = EvtTxQueueStop;

    // Initialize the first default packet context
    NET_PACKET_CONTEXT_ATTRIBUTES myTxContextAttributes;
    NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE(&myTxContextAttributes, MY_DEFAULT_TX_PACKET_CONTEXT);

    // Add the first default packet context attributes to the queue
    status = NetTxQueueInitAddPacketContextAttributes(txQueueInit, &myTxContextAttributes);

    // Get the queue ID
    const ULONG queueId = NetTxQueueInitGetQueueId(txQueueInit);

    // Create the transmit queue
    NETPACKETQUEUE txQueue;
    status = NetTxQueueCreate(
        txQueueInit,
        &txAttributes,
        &txConfig,
        &txQueue);

    // Get the queue context for storing the queue ID and packet extension offset info
    PMY_TX_QUEUE_CONTEXT queueContext = GetMyTxQueueContext(txQueue);

    // Store the queue ID in the context
    queueContext->QueueId = queueId;

    // Query checksum packet extension offset and store it in the context
    NET_PACKET_EXTENSION_QUERY extension;
    NET_PACKET_EXTENSION_QUERY_INIT(
        &extension,
        NET_PACKET_EXTENSION_CHECKSUM_NAME,
        NET_PACKET_EXTENSION_CHECKSUM_VERSION_1);

    queueContext->ChecksumExtensionOffset = NetTxQueueGetPacketExtensionOffset(txQueue, &extension);

    // Query Large Send Offload packet extension offset and store it in the context
    NET_PACKET_EXTENSION_QUERY_INIT(
        &extension,
        NET_PACKET_EXTENSION_LSO_NAME,
        NET_PACKET_EXTENSION_LSO_VERSION_1);
    
    queueContext->LsoExtensionOffset = NetTxQueueGetPacketExtensionOffset(txQueue, &extension);

    return status;
}
```

For more information about packet extensions and available packet extension constants, see [Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions).

## -see-also