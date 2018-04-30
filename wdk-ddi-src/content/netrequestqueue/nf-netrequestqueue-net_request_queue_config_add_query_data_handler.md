---
UID: NF:netrequestqueue.NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER
title: NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER function
author: windows-driver-content
description: Adds a caller-provided handler for a specific OID query data request to a NET_REQUEST_QUEUE_CONFIG structure.
ms.assetid: d448093c-29c5-4517-bb33-9055e5694ebc
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrequestqueue.h
apiname: 
-	NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

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

## -returns
This method does not return a value.

## -remarks
When the client driver has finished adding custom handlers, it registers them with NetAdapterCx by calling [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

If the memory allocation for this method fails, the subsequent call to **NetRequestQueueCreate** returns a failure code.

This function has the same effect as the following call sequence:

   1. [NET_REQUEST_QUEUE_QUERY_DATA_HANDLER_INIT](nf-netrequestqueue-net_request_queue_query_data_handler_init.md)
   2. [NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_initialized_query_data_handler.md)

The minimum NetAdapterCx version for **NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER** is 1.0.

## -see-also