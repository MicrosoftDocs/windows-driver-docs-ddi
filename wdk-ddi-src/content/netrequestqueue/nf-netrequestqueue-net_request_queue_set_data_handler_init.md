---
UID: NF:netrequestqueue.NET_REQUEST_QUEUE_SET_DATA_HANDLER_INIT
title: NET_REQUEST_QUEUE_SET_DATA_HANDLER_INIT function (netrequestqueue.h)
description: Initializes a caller-allocated NET_REQUEST_QUEUE_SET_DATA_HANDLER structure.
tech.root: netvista
ms.assetid: 0b9803b4-438b-459e-849c-5e08fa9f58e5
ms.date: 02/09/2018
ms.topic: function
f1_keywords:
 - "netrequestqueue/NET_REQUEST_QUEUE_SET_DATA_HANDLER_INIT"
ms.keywords: NET_REQUEST_QUEUE_SET_DATA_HANDLER_INIT
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
- NET_REQUEST_QUEUE_SET_DATA_HANDLER_INIT
targetos: Windows
product:
- Windows
---

# NET_REQUEST_QUEUE_SET_DATA_HANDLER_INIT function


## -description



Initializes a caller-allocated [NET_REQUEST_QUEUE_SET_DATA_HANDLER](ns-netrequestqueue-_net_request_queue_set_data_handler.md) structure.

## -parameters

### -param SetDataHandler
A pointer to the driver-allocated [NET_REQUEST_QUEUE_SET_DATA_HANDLER](ns-netrequestqueue-_net_request_queue_set_data_handler.md) structure.

### -param Oid
The NDIS_OID identifier for the request. The value is an OID\_*XXX* code.

### -param EvtRequestSetData
A pointer to the client driver's implementation of an *[EVT_NET_REQUEST_SET_DATA](nc-netrequestqueue-evt_net_request_set_data.md)* event callback function.

### -param MinimumInputLength
The required minimum input length for the request.

## -returns
This method does not return a value.

## -remarks


## -see-also
