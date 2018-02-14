---
UID: NF:netrxqueue.NetRxQueueGetRingBuffer
title: NetRxQueueGetRingBuffer function
author: windows-driver-content
description: Retrieves the net ring buffer for a specified net receive queue structure.
ms.assetid: aad632fe-9e36-4d1a-98bd-5a6a4ad1a4e4
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRxQueueGetRingBuffer
req.header: netrxqueue.h
req.include-header: netadaptercx.h
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
-	HeaderDef
apilocation: 
-	netrxqueue.h
apiname: 
-	NetRxQueueGetRingBuffer
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRxQueueGetRingBuffer function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Retrieves the net ring buffer for a specified net receive queue structure.

## -parameters

### -param NetRxQueue
A handle to a net receive queue object.

## -returns
Returns a pointer to the [NET_RING_BUFFER](../netringbuffer/ns-netringbuffer-_net_ring_buffer.md) structure associated with a net receive queue.

## -remarks
The minimum NetAdapterCx version for **NetRxQueueGetRingBuffer** is 1.0.

## -see-also