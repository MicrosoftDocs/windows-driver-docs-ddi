---
UID: NF:netrxqueue.NetRxQueueGetBufferLayoutHint
title: NetRxQueueGetBufferLayoutHint function
author: windows-driver-content
description: The NetRxQueueGetBufferLayoutHint method queries buffer layout hints that a net receive queue can use to calculate how much padding its receive buffers should have.
ms.assetid: ee51f39b-8d5d-45f1-9c29-6021ea25fa52
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRxQueueGetBufferLayoutHint
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
-	NetRxQueueGetBufferLayoutHint
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRxQueueGetBufferLayoutHint function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NetRxQueueGetBufferLayoutHint** method queries buffer layout hints that a net receive queue can use to calculate how much padding its receive buffers should have.

## -parameters

### -param NetRxQueue
A handle to a NETRXQUEUE object obtained from a prior call to [NetRxQueueCreate](nf-netrxqueue-netrxqueuecreate.md).

### -param BufferLayoutHint
A [NET_RXQUEUE_BUFFER_LAYOUT_HINT](ns-netrxqueue-_net_rxqueue_buffer_layout_hint.md) structure that represents the buffer layout hints returned from the upper layer.

## -returns
This method does not return a value.

## -remarks
Call this method to obtain buffer layout hints from the upper layer, formatted as a [NET_RXQUEUE_BUFFER_LAYOUT_HINT](ns-netrxqueue-_net_rxqueue_buffer_layout_hint.md) structure. While this method is optional for client drivers to call, it can help improve receive queue performance by ensuring that protocol headers are naturally aligned.

The minimum NetAdapterCx version for **NetRxQueueGetBufferLayoutHint** is 1.1.

## -see-also