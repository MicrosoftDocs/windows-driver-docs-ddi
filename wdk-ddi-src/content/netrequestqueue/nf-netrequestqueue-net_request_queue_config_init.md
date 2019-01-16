---
UID: NF:netrequestqueue.NET_REQUEST_QUEUE_CONFIG_INIT
title: NET_REQUEST_QUEUE_CONFIG_INIT function
description: Initializes a caller-allocated NET_REQUEST_QUEUE_CONFIG structure.
tech.root: netvista
ms.assetid: 4eaf1360-d120-4585-8792-8a2c632e744f
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NET_REQUEST_QUEUE_CONFIG_INIT
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrequestqueue.h
apiname: 
-	NET_REQUEST_QUEUE_CONFIG_INIT
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NET_REQUEST_QUEUE_CONFIG_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Initializes a caller-allocated [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure.

## -parameters

### -param NetRequestQueueConfig
A pointer to a driver-allocated [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure.

### -param Adapter
The net adapter object that the client created in a prior call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

### -param QueueType
A [NET_REQUEST_QUEUE_TYPE](ne-netrequestqueue-_net_request_queue_type.md) enumeration that specifies the type of queue.

## -returns
This method does not return a value.

## -remarks


## -see-also
