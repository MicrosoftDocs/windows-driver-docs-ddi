---
UID: NF:nettxqueue.NetTxQueueGetRingBuffer
title: NetTxQueueGetRingBuffer function
author: windows-driver-content
description: Retrieves the net ring buffer for a specified net transmit queue structure.
ms.assetid: 57d8236a-0046-481a-9688-12a0ad1aba43
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetTxQueueGetRingBuffer
req.header: nettxqueue.h
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
-	nettxqueue.h
apiname: 
-	NetTxQueueGetRingBuffer
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetTxQueueGetRingBuffer function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Retrieves the net ring buffer for a specified net transmit queue structure.

## -parameters

### -param NetTxQueue
A handle to a net transmit queue object.

## -returns
Returns a pointer to the NET_RING_BUFFER structure associated with a net transmit queue structure.

## -remarks
The minimum NetAdapterCx version for **NetTxQueueGetRingBuffer** is 1.0.

## -see-also