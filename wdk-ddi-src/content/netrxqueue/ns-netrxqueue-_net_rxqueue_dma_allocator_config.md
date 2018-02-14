---
UID: NS:netrxqueue._NET_RXQUEUE_DMA_ALLOCATOR_CONFIG
title: _NET_RXQUEUE_DMA_ALLOCATOR_CONFIG
author: windows-driver-content
description: The NET_RXQUEUE_DMA_ALLOCATOR_CONFIG structure describes the configuration options for a DMA allocator to be associated with a receive queue.
ms.assetid: ecee069f-a231-4155-8313-267d422f1c4f
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_RXQUEUE_DMA_ALLOCATOR_CONFIG, NET_RXQUEUE_DMA_ALLOCATOR_CONFIG, *PNET_RXQUEUE_DMA_ALLOCATOR_CONFIG, 
req.header: netrxqueue.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_RXQUEUE_DMA_ALLOCATOR_CONFIG, *PNET_RXQUEUE_DMA_ALLOCATOR_CONFIG
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrxqueue.h
apiname: 
-	NET_RXQUEUE_DMA_ALLOCATOR_CONFIG
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_RXQUEUE_DMA_ALLOCATOR_CONFIG structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_RXQUEUE_DMA_ALLOCATOR_CONFIG** structure describes the configuration options for a DMA allocator to be associated with a receive queue.

## -struct-fields

### -field Size
The size of this structure, in bytes.
 
### -field DmaEnabler
The DMA enabler to use when allocating receive buffers.
 
### -field MaximumPhysicalAddress
The maximum logical address to use when allocating receive buffers. Set to **0** to indicate to NetAdapterCx that there is no maximum address.
 
### -field CacheEnabled
A [WDF_TRI_STATE](../wdftypes/ne-wdftypes-_wdf_tri_state.md) value defining if the memory allocated should have cache enabled or not. A value of **WdfUseDefault** will enable cache only if the device is cache coherent.
 
### -field PreferredNode
The preferred NUMA node to use when allocating memory. If this member is set to **MM_ANY_NODE_OK**, NetAdapterCx will automatically determine the best node to use.

## -remarks
Call [NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT](nf-netrxqueue-net_rxqueue_dma_allocator_config_init.md) to initialize this structure.

The **NET_RXQUEUE_DMA_ALLOCATOR_CONFIG** structure is an input parameter to [NetRxQueueInitSetDmaAllocatorConfig](nf-netrxqueue-netrxqueueinitsetdmaallocatorconfig.md). The client must use **NET_RXQUEUE_DMA_ALLOCATOR_CONFIG_INIT** to initialize this structure before calling **NetRxQueueInitSetDmaAllocatorConfig**.

The minimum NetAdapterCx version for **NET_RXQUEUE_DMA_ALLOCATOR_CONFIG** is 1.1.

## -see-also