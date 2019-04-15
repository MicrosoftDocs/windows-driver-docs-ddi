---
UID: NE:netrequestqueue._NET_REQUEST_QUEUE_TYPE
title: _NET_REQUEST_QUEUE_TYPE (netrequestqueue.h)
description: Specifies the type of net request queue.
tech.root: netvista
ms.assetid: af41472a-ee4b-4bbe-8eac-4ac9b80fd629
ms.date: 02/09/2018
ms.topic: enum
ms.keywords: _NET_REQUEST_QUEUE_TYPE, NET_REQUEST_QUEUE_TYPE, 
req.header: netrequestqueue.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_REQUEST_QUEUE_TYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequestqueue.h
api_name: 
- NET_REQUEST_QUEUE_TYPE
product:
- Windows
targetos: Windows
product:
- Windows
---

# _NET_REQUEST_QUEUE_TYPE enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Specifies the type of net request queue.

## -enum-fields

### -field NetRequestQueueTypeInvalid : 
Not supported.

### -field NetRequestQueueDefaultSequential : 
Specifies that the queue supports sequential delivery (normal control requests, or OIDs).

### -field NetRequestQueueDefaultParallel : 
Specifies that the queue supports parallel dispatching (direct control requests, or OIDs).

## -remarks
The **NET_REQUEST_QUEUE_TYPE** enumeration is used to specify queue type in the [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure.

The client driver passes an initialized **NET_REQUEST_QUEUE_CONFIG** structure as an input parameter value to [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).



## -see-also
