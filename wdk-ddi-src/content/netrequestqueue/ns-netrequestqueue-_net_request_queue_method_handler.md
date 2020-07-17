---
UID: NS:netrequestqueue._NET_REQUEST_QUEUE_METHOD_HANDLER
title: _NET_REQUEST_QUEUE_METHOD_HANDLER (netrequestqueue.h)
description: Reserved for internal use. Call NET_REQUEST_QUEUE_CONFIG_ADD_METHOD_HANDLER to add a caller-provided handler for a specific OID method request.
tech.root: netvista
ms.assetid: 70770bd2-4ab6-42c5-abd4-88a41ad8553a
ms.date: 02/09/2018
keywords: ["_NET_REQUEST_QUEUE_METHOD_HANDLER structure"]
f1_keywords:
 - "netrequestqueue/NET_REQUEST_QUEUE_METHOD_HANDLER"
 - "NET_REQUEST_QUEUE_METHOD_HANDLER"
ms.keywords: _NET_REQUEST_QUEUE_METHOD_HANDLER, *PNET_REQUEST_QUEUE_METHOD_HANDLER, NET_REQUEST_QUEUE_METHOD_HANDLER, 
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
req.typenames: NET_REQUEST_QUEUE_METHOD_HANDLER, *PNET_REQUEST_QUEUE_METHOD_HANDLER
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequestqueue.h
api_name: 
- NET_REQUEST_QUEUE_METHOD_HANDLER
targetos: Windows
product:
- Windows
---

# _NET_REQUEST_QUEUE_METHOD_HANDLER structure

## -description



Reserved for internal use. Call [NET_REQUEST_QUEUE_CONFIG_ADD_METHOD_HANDLER](nf-netrequestqueue-net_request_queue_config_add_method_handler.md) to add a caller-provided handler for a specific OID method request.

## -struct-fields

### -field Next
A pointer to the next custom handler.

### -field Memory
Reserved for internal use.

### -field Oid
Specifies the object identifier of the requested operation. The value is an OID\_*XXX* code. 

### -field EvtRequestMethod
A pointer to the client driver's implementation of an *[EVT_NET_REQUEST_METHOD](nc-netrequestqueue-evt_net_request_method.md)* event callback function.

### -field MinimumInputLength
The minimum input length needed by the client for this request.

### -field MinimumOutputLength
The minimum output length needed by the client for this request.

## -remarks


## -see-also
