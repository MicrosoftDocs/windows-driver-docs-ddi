---
UID: NA:netrequestqueue
ms.assetid: 659e65a6-0c1c-34ef-aa27-96d03d945660
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netrequestqueue.h header



This header is used by NetAdapterCx client drivers. For more information, see
- [Network Adapter WDF Class Extension (Cx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/)

Netrequestqueue.h contains these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_METHOD_HANDLER function](nf-netrequestqueue-net_request_queue_config_add_initialized_method_handler.md) | Adds a caller-provided, pre-initialized custom method request handler structure to a NET_REQUEST_QUEUE_CONFIG structure. |
| [NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER function](nf-netrequestqueue-net_request_queue_config_add_initialized_query_data_handler.md) | Adds a caller-provided, pre-initialized query request handler structure to a NET_REQUEST_QUEUE_CONFIG structure. |
| [NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_SET_DATA_HANDLER function](nf-netrequestqueue-net_request_queue_config_add_initialized_set_data_handler.md) | Adds a caller-provided, pre-initialized set request handler structure to a NET_REQUEST_QUEUE_CONFIG structure. |
| [NET_REQUEST_QUEUE_CONFIG_ADD_METHOD_HANDLER function](nf-netrequestqueue-net_request_queue_config_add_method_handler.md) | Adds a caller-provided handler for a specific OID method request to a NET_REQUEST_QUEUE_CONFIG structure. |
| [NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER function](nf-netrequestqueue-net_request_queue_config_add_query_data_handler.md) | Adds a caller-provided handler for a specific OID query data request to a NET_REQUEST_QUEUE_CONFIG structure. |
| [NET_REQUEST_QUEUE_CONFIG_ADD_SET_DATA_HANDLER function](nf-netrequestqueue-net_request_queue_config_add_set_data_handler.md) | Adds a caller-provided handler for a specific OID set data request to a NET_REQUEST_QUEUE_CONFIG structure. |
| [NET_REQUEST_QUEUE_CONFIG_INIT function](nf-netrequestqueue-net_request_queue_config_init.md) | Initializes a caller-allocated NET_REQUEST_QUEUE_CONFIG structure. |
| [NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL function](nf-netrequestqueue-net_request_queue_config_init_default_parallel.md) | Initializes a caller-allocated NET_REQUEST_QUEUE_CONFIG structure to create a default parallel request queue for direct control requests (OIDs). |
| [NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_SEQUENTIAL function](nf-netrequestqueue-net_request_queue_config_init_default_sequential.md) | Initializes a caller-allocated NET_REQUEST_QUEUE_CONFIG structure to create a default sequential request queue for normal control requests (OIDs). |
| [NET_REQUEST_QUEUE_METHOD_HANDLER_INIT function](nf-netrequestqueue-net_request_queue_method_handler_init.md) | Initializes a caller-allocated NET_REQUEST_QUEUE_METHOD_HANDLER structure. |
| [NET_REQUEST_QUEUE_QUERY_DATA_HANDLER_INIT function](nf-netrequestqueue-net_request_queue_query_data_handler_init.md) | Initializes a caller-allocated NET_REQUEST_QUEUE_QUERY_DATA_HANDLER structure. |
| [NET_REQUEST_QUEUE_SET_DATA_HANDLER_INIT function](nf-netrequestqueue-net_request_queue_set_data_handler_init.md) | TBD |
| [NetRequestQueueCreate function](nf-netrequestqueue-netrequestqueuecreate.md) | Creates a net request queue object. |
| [NetRequestQueueGetAdapter function](nf-netrequestqueue-netrequestqueuegetadapter.md) | Retrieves the NETADAPTER object corresponding to a NETREQUESTQUEUE. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_NET_REQUEST_DEFAULT callback function](nc-netrequestqueue-evt_net_request_default.md) | Implemented by the client driver as the default handler for object identifier (OID) requests that are not query, set, or method requests. |
| [EVT_NET_REQUEST_DEFAULT_METHOD callback function](nc-netrequestqueue-evt_net_request_default_method.md) | Implemented by the client driver as the default handler for method object identifier (OID) requests. |
| [EVT_NET_REQUEST_DEFAULT_QUERY_DATA callback function](nc-netrequestqueue-evt_net_request_default_query_data.md) | Implemented by the client driver as the default handler for query object identifier (OID) requests. |
| [EVT_NET_REQUEST_DEFAULT_SET_DATA callback function](nc-netrequestqueue-evt_net_request_default_set_data.md) | Implemented by the client driver as the default handler for set object identifier (OID) requests. |
| [EVT_NET_REQUEST_METHOD callback function](nc-netrequestqueue-evt_net_request_method.md) | Implemented by the client driver to handle a specific method OID request. |
| [EVT_NET_REQUEST_QUERY_DATA callback function](nc-netrequestqueue-evt_net_request_query_data.md) | Implemented by the client driver to handle a specific OID query request. |
| [EVT_NET_REQUEST_SET_DATA callback function](nc-netrequestqueue-evt_net_request_set_data.md) | Implemented by the client driver to handle a specific OID set request. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_REQUEST_QUEUE_CONFIG structure](ns-netrequestqueue-_net_request_queue_config.md) | The NET_REQUEST_QUEUE_CONFIG structure represents configuration information for a net request queue. |
| [_NET_REQUEST_QUEUE_METHOD_HANDLER structure](ns-netrequestqueue-_net_request_queue_method_handler.md) | Reserved for internal use. Call NET_REQUEST_QUEUE_CONFIG_ADD_METHOD_HANDLER to add a caller-provided handler for a specific OID method request. |
| [_NET_REQUEST_QUEUE_QUERY_DATA_HANDLER structure](ns-netrequestqueue-_net_request_queue_query_data_handler.md) | Reserved for internal use. Call NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER to add a caller-provided handler for a specific OID query request. |
| [_NET_REQUEST_QUEUE_SET_DATA_HANDLER structure](ns-netrequestqueue-_net_request_queue_set_data_handler.md) | Reserved for internal use. Call NET_REQUEST_QUEUE_CONFIG_ADD_SET_DATA_HANDLER to add a caller-provided handler for a specific OID set request. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_NET_REQUEST_QUEUE_TYPE enumeration](ne-netrequestqueue-_net_request_queue_type.md) | Specifies the type of net request queue. |
