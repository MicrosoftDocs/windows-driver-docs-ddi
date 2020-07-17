---
UID: NF:netrequestqueue.NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER
title: NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER function (netrequestqueue.h)
description: Adds a caller-provided handler for a specific OID query data request to a NET_REQUEST_QUEUE_CONFIG structure.
tech.root: netvista
ms.assetid: d448093c-29c5-4517-bb33-9055e5694ebc
ms.date: 02/09/2018
keywords: ["NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER function"]
f1_keywords:
 - "netrequestqueue/NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER"
 - "NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER"
ms.keywords: NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER
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
- NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER
targetos: Windows
product:
- Windows
---

# NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER function


## -description



Adds a caller-provided handler for a specific OID query data request to a [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure.

## -parameters

### -param NetRequestQueueConfig
A pointer to a driver-allocated [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure to which the custom handler is being added.

### -param Oid
The object identifier of the requested operation. The value is an OID\_*XXX* code.

### -param EvtRequestQueryData
A pointer to the client driver's implementation of a *[EVT_NET_REQUEST_QUERY_DATA](nc-netrequestqueue-evt_net_request_query_data.md)* event callback function.

### -param MinimumOutputLength
A UINT specifying the minimum output length for the request.

## -remarks
When the client driver has finished adding custom handlers, it registers them with NetAdapterCx by calling [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

If the memory allocation for this method fails, the subsequent call to **NetRequestQueueCreate** returns a failure code.

This function has the same effect as the following call sequence:

   1. [NET_REQUEST_QUEUE_QUERY_DATA_HANDLER_INIT](nf-netrequestqueue-net_request_queue_query_data_handler_init.md)
   2. [NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_initialized_query_data_handler.md)



## -see-also
