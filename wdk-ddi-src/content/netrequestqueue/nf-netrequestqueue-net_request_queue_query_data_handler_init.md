---
UID: NF:netrequestqueue.NET_REQUEST_QUEUE_QUERY_DATA_HANDLER_INIT
title: NET_REQUEST_QUEUE_QUERY_DATA_HANDLER_INIT function
description: Initializes a caller-allocated NET_REQUEST_QUEUE_QUERY_DATA_HANDLER structure.
tech.root: netvista
ms.assetid: 61193100-87c9-4e2b-b268-cb6ae36e6503
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NET_REQUEST_QUEUE_QUERY_DATA_HANDLER_INIT
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
-	NET_REQUEST_QUEUE_QUERY_DATA_HANDLER_INIT
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NET_REQUEST_QUEUE_QUERY_DATA_HANDLER_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Initializes a caller-allocated [NET_REQUEST_QUEUE_QUERY_DATA_HANDLER](ns-netrequestqueue-_net_request_queue_query_data_handler.md) structure.

## -parameters

### -param QueryDataHandler
A pointer to the driver-allocated [NET_REQUEST_QUEUE_QUERY_DATA_HANDLER](ns-netrequestqueue-_net_request_queue_query_data_handler.md) structure.

### -param Oid
The NDIS_OID identifier for the request. The value is an OID\_*XXX* code.

### -param EvtRequestQueryData
A pointer to the client driver's implementation of an *[EVT_NET_REQUEST_QUERY_DATA](nc-netrequestqueue-evt_net_request_query_data.md)* event callback function.

### -param MinimumOutputLength
The required minimum output length for the request.

## -returns
This method does not return a value.

## -remarks


## -see-also
