---
UID: NF:netrxqueue.NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT
title: NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT function
author: windows-driver-content
description: The NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT method initializes a NET_RXQUEUE_DMA_ALLOCATOR_CONFIG structure.
ms.assetid: f9e72b4e-1552-4837-844b-432033509fcb
ms.author: windowsdriverdev
ms.date: 02/09/2019
ms.topic: function
ms.keywords: NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT
req.header: netrxqueue.h
req.include-header:
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
-	NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT** method initializes a [NET_RXQUEUE_DMA_ALLOCATOR_CONFIG](ns-netrxqueue-_net_rxqueue_dma_allocator_config.md) structure.

## -parameters

### -param DmaAllocatorConfig
A pointer to the [NET_RXQUEUE_DMA_ALLOCATOR_CONFIG](ns-netrxqueue-_net_rxqueue_dma_allocator_config.md) structure to be initialized.

### -param DmaEnabler
A handle to a DMA enabler object that the client driver obtained from a previous call to [WdfDmaEnablerCreate](../wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate.md). 

## -returns
This method does not return a value.

## -remarks
**NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT** is used to initialize a [NET_RXQUEUE_DMA_ALLOCATOR_CONFIG](ns-netrxqueue-_net_rxqueue_dma_allocator_config.md) structure, which is passed as an input parameter to [NetRxQueueInitSetDmaAllocatorConfig](nf-netrxqueue-netrxqueueinitsetdmaallocatorconfig.md).

The minimum NetAdapterCx version for **NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT** is 1.1.

## -see-also