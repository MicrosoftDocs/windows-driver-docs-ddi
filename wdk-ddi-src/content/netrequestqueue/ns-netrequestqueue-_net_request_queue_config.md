---
UID: NS:netrequestqueue._NET_REQUEST_QUEUE_CONFIG
title: _NET_REQUEST_QUEUE_CONFIG
description: The NET_REQUEST_QUEUE_CONFIG structure represents configuration information for a net request queue.
tech.root: netvista
ms.assetid: bdb3062f-81c4-4fa2-bc7a-ce5bd9330220
ms.date: 02/09/2018
ms.topic: struct
ms.keywords: _NET_REQUEST_QUEUE_CONFIG, *PNET_REQUEST_QUEUE_CONFIG, NET_REQUEST_QUEUE_CONFIG, 
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
req.typenames: NET_REQUEST_QUEUE_CONFIG, *PNET_REQUEST_QUEUE_CONFIG
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrequestqueue.h
apiname: 
-	NET_REQUEST_QUEUE_CONFIG
product:
-	Windows
targetos: Windows
product:
- Windows
---

# _NET_REQUEST_QUEUE_CONFIG structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The NET_REQUEST_QUEUE_CONFIG structure represents configuration information for a net request queue.

## -struct-fields

### -field Size
The size of this structure, in bytes.
 
### -field Adapter
The net adapter object that the client created in a prior call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).
 
### -field Type
A [NET_REQUEST_QUEUE_TYPE](ne-netrequestqueue-_net_request_queue_type.md) enumeration that specifies the type of queue.
 
### -field EvtRequestDefaultSetData
A pointer to the client driver's implementation of the *[EVT_NET_REQUEST_DEFAULT_SET_DATA](nc-netrequestqueue-evt_net_request_default_set_data.md)* event callback function.

### -field EvtRequestDefaultQueryData
A pointer to the client driver's implementation of the *[EVT_NET_REQUEST_DEFAULT_QUERY_DATA](nc-netrequestqueue-evt_net_request_default_query_data.md)* event callback function.

### -field EvtRequestDefaultMethod
A pointer to the client driver's implementation of the *[EVT_NET_REQUEST_DEFAULT_METHOD](nc-netrequestqueue-evt_net_request_default_method.md)* event callback function.

### -field EvtRequestDefault
A pointer to the client driver's implementation of the *[EVT_NET_REQUEST_DEFAULT](nc-netrequestqueue-evt_net_request_default.md)* event callback function.

### -field AddHandlerError
A bit field tracking any errors encountered during operations to add custom handlers.

### -field SizeOfSetDataHandler
A ULONG that specifies the size of the **SetDataHandlers** member.

### -field SizeOfQueryDataHandler
A ULONG that specifies the size of the **QueryDataHandlers** member.

### -field SizeOfMethodHandler
A ULONG that specifies the size of the **MethodHandlers** member.

### -field SetDataHandlers
A pointer to the first [NET_REQUEST_QUEUE_SET_DATA_HANDLER](ns-netrequestqueue-_net_request_queue_set_data_handler.md) structure of the list of custom set request handlers.

### -field QueryDataHandlers
A pointer to the first [NET_REQUEST_QUEUE_QUERY_DATA_HANDLER](ns-netrequestqueue-_net_request_queue_query_data_handler.md) structure of the list of custom query request handlers.

### -field MethodHandlers
A pointer to the first [NET_REQUEST_QUEUE_METHOD_HANDLER](ns-netrequestqueue-_net_request_queue_method_handler.md) structure of the list of custom method request handlers.

## -remarks
The client driver must call [NET_REQUEST_QUEUE_CONFIG_INIT](nf-netrequestqueue-net_request_queue_config_init.md) to initialize this structure.

The client driver passes an initialized **NET_REQUEST_QUEUE_CONFIG** structure as an input parameter value to [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).



## -see-also
