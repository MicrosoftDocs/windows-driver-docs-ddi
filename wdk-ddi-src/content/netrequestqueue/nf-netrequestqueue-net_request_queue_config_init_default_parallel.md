---
UID: NF:netrequestqueue.NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL
title: NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL function (netrequestqueue.h)
description: Initializes a caller-allocated NET_REQUEST_QUEUE_CONFIG structure to create a default parallel request queue for direct control requests (OIDs).
tech.root: netvista
ms.assetid: ce15213c-985a-4718-bace-d2a19f591d40
ms.date: 02/09/2018
keywords: ["NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL function"]
f1_keywords:
 - "netrequestqueue/NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL"
 - "NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL"
ms.keywords: NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL
req.header: netrequestqueue.h
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
req.alt-api:
req.alt-loc:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequestqueue.h
api_name: 
- NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL
targetos: Windows
product:
- Windows
---

# NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL function


## -description



Initializes a caller-allocated [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure to create a default parallel request queue for direct control requests (OIDs).

## -parameters

### -param NetRequestQueueConfig
A pointer to a driver-allocated [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure.

### -param Adapter
The net adapter object that the client created in a prior call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

## -remarks


## -see-also
