---
UID: NF:netrequestqueue.NetRequestQueueGetAdapter
title: NetRequestQueueGetAdapter function (netrequestqueue.h)
description: Retrieves the NETADAPTER object corresponding to a NETREQUESTQUEUE.
tech.root: netvista
ms.assetid: 638f5dea-d79b-41bb-967b-27339bfae3ab
ms.date: 02/01/2019
keywords: ["NetRequestQueueGetAdapter function"]
f1_keywords:
 - "netrequestqueue/NET_REQUEST_QUEUE_TYPE"
 - "NET_REQUEST_QUEUE_TYPE"
ms.keywords: NetRequestQueueGetAdapter
req.header: netrequestqueue.h
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
- apiref
apitype: 
- HeaderDef
apilocation: 
- netrequestqueue.h
apiname: 
- NetRequestQueueGetAdapter
targetos: Windows
---

# NetRequestQueueGetAdapter function


## -description



Retrieves the NETADAPTER object corresponding to a NETREQUESTQUEUE.

## -parameters

### -param RequestQueue
A handle to the NETREQUESTQUEUE object.

## -returns
Returns the net adapter object that the client created in a prior call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

## -remarks


## -see-also
