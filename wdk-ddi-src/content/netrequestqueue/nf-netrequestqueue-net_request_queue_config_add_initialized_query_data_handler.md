---
UID: NF:netrequestqueue.NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER
title: NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER function (netrequestqueue.h)
description: Adds a caller-provided, pre-initialized query request handler structure to a NET_REQUEST_QUEUE_CONFIG structure.
tech.root: netvista
ms.assetid: 3c194a5c-2154-448e-bf83-4400acedc1f4
ms.date: 02/09/2018
ms.topic: function
f1_keywords:
 - "netrequestqueue/NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER"
ms.keywords: NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER
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
- NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER
targetos: Windows
product:
- Windows
---

# NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER function


## -description



Adds a caller-provided, pre-initialized query request handler structure to a [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure.

## -parameters

### -param NetRequestQueueConfig
A pointer to a driver-allocated [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure to which the query data handler is being added.

### -param QueryDataHandler
A pointer to a driver-allocated and initialized [NET_REQUEST_QUEUE_QUERY_DATA_HANDLER](ns-netrequestqueue-_net_request_queue_query_data_handler.md) structure. The client driver must call [NET_REQUEST_QUEUE_QUERY_DATA_HANDLER_INIT](nf-netrequestqueue-net_request_queue_query_data_handler_init.md) method to initialize the custom handler before calling this function.

## -returns
This method does not return a value.

## -remarks
When the client driver has finished adding custom handlers, it registers them with NetAdapterCx by calling [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

If the memory allocation for this method fails, the subsequent call to **NetRequestQueueCreate** returns a failure code.



## -see-also

[NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md)

[NET_REQUEST_QUEUE_QUERY_DATA_HANDLER](ns-netrequestqueue-_net_request_queue_query_data_handler.md)
