---
UID: NF:netrxqueue.NetRxQueueQueryAllocatorCacheEnabled
title: NetRxQueueQueryAllocatorCacheEnabled function
author: windows-driver-content
description: The NetRxQueueQueryAllocatorCacheEnabled method queries whether DMA allocator memory is cacheable.
ms.assetid: 1864f61a-3e49-4152-8149-5de96651495f
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRxQueueQueryAllocatorCacheEnabled
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
-	NetRxQueueQueryAllocatorCacheEnabled
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRxQueueQueryAllocatorCacheEnabled function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NetRxQueueQueryAllocatorCacheEnabled** method queries whether DMA allocator memory is cacheable.

## -parameters

### -param RxQueue
The receive queue object that the client driver obtained from a previous call to [NetRxQueueCreate](nf-netrxqueue-netrxqueuecreate.md).

### -param CacheEnabled
A pointer to a boolean value that, on return, indicates whether the memory allocated for the Rx queue's payload buffers is cacheable.

## -returns
This method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The minimum NetAdapterCx version for **NetRxQueueQueryAllocatorCacheEnabled** is 1.1.

## -see-also

[NET_RXQUEUE_CONFIG](ns-netrxqueue-_net_rxqueue_config.md)