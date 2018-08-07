---
UID: NS:netrequestqueue._NET_REQUEST_QUEUE_SET_DATA_HANDLER
title: _NET_REQUEST_QUEUE_SET_DATA_HANDLER
author: windows-driver-content
description: Reserved for internal use. Call NET_REQUEST_QUEUE_CONFIG_ADD_SET_DATA_HANDLER to add a caller-provided handler for a specific OID set request.
ms.assetid: c5af08b7-0733-481d-a6ba-32a21dd7990f
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_REQUEST_QUEUE_SET_DATA_HANDLER, *PNET_REQUEST_QUEUE_SET_DATA_HANDLER, NET_REQUEST_QUEUE_SET_DATA_HANDLER, 
req.header: netrequestqueue.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_REQUEST_QUEUE_SET_DATA_HANDLER, *PNET_REQUEST_QUEUE_SET_DATA_HANDLER
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrequestqueue.h
apiname: 
-	NET_REQUEST_QUEUE_SET_DATA_HANDLER
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_REQUEST_QUEUE_SET_DATA_HANDLER structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Reserved for internal use. Call [NET_REQUEST_QUEUE_CONFIG_ADD_SET_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_set_data_handler.md) to add a caller-provided handler for a specific OID set request.

## -struct-fields

### -field Next
A pointer to the next custom handler.
 
### -field Memory
Reserved for internal use.
 
### -field Oid
Specifies the object identifier of the requested operation. The value is an OID\_*XXX* code. 
 
### -field EvtRequestSetData
A pointer to the client driver's implementation of an *[EVT_NET_REQUEST_SET_DATA](nc-netrequestqueue-evt_net_request_set_data.md)* event callback function.
 
### -field MinimumInputLength
The minimum input length needed by the client for this request.
 
### -field MinimumOutputLength
The minimum output length needed by the client for this request.

## -remarks


## -see-also