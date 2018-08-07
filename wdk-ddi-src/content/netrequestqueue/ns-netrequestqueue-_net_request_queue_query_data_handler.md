---
UID: NS:netrequestqueue._NET_REQUEST_QUEUE_QUERY_DATA_HANDLER
title: _NET_REQUEST_QUEUE_QUERY_DATA_HANDLER
author: windows-driver-content
description: Reserved for internal use. Call NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER to add a caller-provided handler for a specific OID query request.
ms.assetid: 115c57d3-3816-42c5-aaf5-0b92ffb7dbf1
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_REQUEST_QUEUE_QUERY_DATA_HANDLER, *PNET_REQUEST_QUEUE_QUERY_DATA_HANDLER, NET_REQUEST_QUEUE_QUERY_DATA_HANDLER, 
req.header: netrequestqueue.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_REQUEST_QUEUE_QUERY_DATA_HANDLER, *PNET_REQUEST_QUEUE_QUERY_DATA_HANDLER
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrequestqueue.h
apiname: 
-	NET_REQUEST_QUEUE_QUERY_DATA_HANDLER
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_REQUEST_QUEUE_QUERY_DATA_HANDLER structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Reserved for internal use. Call [NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_query_data_handler.md) to add a caller-provided handler for a specific OID query request.

## -struct-fields

### -field Next
A pointer to the next custom handler.
 
### -field Memory
Reserved for internal use.
 
### -field Oid
Specifies the object identifier of the requested operation. The value is an OID\_*XXX* code. 
 
### -field EvtRequestQueryData
A pointer to the client driver's implementation of an *[EVT_NET_REQUEST_QUERY_DATA](nc-netrequestqueue-evt_net_request_query_data.md)* event callback function.
 
### -field MinimumInputLength
The minimum input length needed by the client for this request.
 
### -field MinimumOutputLength
The minimum output length needed by the client for this request.

## -remarks


## -see-also