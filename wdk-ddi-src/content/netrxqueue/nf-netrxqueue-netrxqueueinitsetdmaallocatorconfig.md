---
UID: NF:netrxqueue.NetRxQueueInitSetDmaAllocatorConfig
title: NetRxQueueInitSetDmaAllocatorConfig function
author: windows-driver-content
description: The NetRxQueueInitSetDmaAllocatorConfig method associates an initialized NET_RXQUEUE_DMA_ALLOCATOR_CONFIG structure with a receive queue.
ms.assetid: ecfe1d9b-7a28-45e2-9e44-46dcfa97f610
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRxQueueInitSetDmaAllocatorConfig
req.header: netrxqueue.h
req.include-header: netadaptercx.h
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
-	HeaderDef
apilocation: 
-	netrxqueue.h
apiname: 
-	NetRxQueueInitSetDmaAllocatorConfig
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRxQueueInitSetDmaAllocatorConfig function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The NetRxQueueInitSetDmaAllocatorConfig method associates an initialized NET_RXQUEUE_DMA_ALLOCATOR_CONFIG structure with a receive queue.

## -parameters

### -param NetRxQueueInit
A pointer to the **NETRXQUEUE_INIT** structure that the client driver received in *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)*.

### -param DmaAllocatorConfig
A pointer to a [NET_RXQUEUE_DMA_ALLOCATOR_CONFIG](ns-netrxqueue-_net_rxqueue_dma_allocator_config.md) structure the driver initialized with a previous call to [NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT](nf-netrxqueue-net_rxqueue_dma_allocator_config_init.md).

## -returns
This method does not return a value.

## -remarks
The **NETRXQUEUE_INIT** structure is an opaque structure that is defined and allocated by NetAdapterCx, similar to **WDFDEVICE_INIT**.

In NetAdapterCx version 1.1, this method replaced the previous **NetRxQueueConfigureDmaAllocator** method as the way a client driver lets NetAdapterCx manage the receive buffer. To opt in, follow these steps in your *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* callback function:

1. Set the **AllocationSize** and **AlignmentRequirement** members of the [NET_RXQUEUE_CONFIG](ns-netrxqueue-_net_rxqueue_config.md) structure.
2. Allocate a [NET_RXQUEUE_DMA_ALLOCATOR_CONFIG](ns-netrxqueue-_net_rxqueue_dma_allocator_config.md) structure.
3. Call [NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT](nf-netrxqueue-net_rxqueue_dma_allocator_config_init.md) with the **NET_RXQUEUE_DMA_ALLOCATOR_CONFIG** structure and a DMA enabler object retrieved from the NETADAPTER's context.
4. Call **NetRxQueueInitSetDmaAllocatorConfig** with the initialized **NET_RXQUEUE_DMA_ALLOCATOR_CONFIG** structure.

NetAdapterCx then uses the queue's DMA enabler to allocate pre-mapped buffers for each packet in the queue's [NET_RING_BUFFER](../netringbuffer/ns-netringbuffer-_net_ring_buffer.md) structure, and updates the **VirtualAddress** and **DmaLogicalAddress** members of each [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) to point to each premapped buffer.

The client driver retrieves a pointer to the ring buffer by calling [NetRxQueueGetRingBuffer](nf-netrxqueue-netrxqueuegetringbuffer.md).

The minimum NetAdapterCx version for **NetRxQueueInitSetDmaAllocatorConfig** is 1.1.

## -see-also