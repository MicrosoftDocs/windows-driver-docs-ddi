---
UID: NC:netrequestqueue.EVT_NET_REQUEST_QUERY_DATA
title: EVT_NET_REQUEST_QUERY_DATA (netrequestqueue.h)
description: Implemented by the client driver to handle a specific OID query request.
tech.root: netvista
ms.assetid: 1ae913de-77da-4622-9a79-72a34e4705ab
ms.date: 02/08/2018
ms.topic: callback
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
- apiref
apitype: 
- UserDefined
apilocation: 
- netrequestqueue.h
apiname: 
- EVT_NET_REQUEST_QUERY_DATA
product:
- Windows
targetos: Windows
product:
- Windows
---

# EVT_NET_REQUEST_QUERY_DATA callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Implemented by the client driver to handle a specific OID query request.

## -prototype

```c++
//Declaration

EVT_NET_REQUEST_QUERY_DATA EvtNetRequestQueryData; 

// Definition

VOID EvtNetRequestQueryData 
(
	_In_	NETREQUESTQUEUE	RequestQueue,
	_In_	NETREQUEST 		Request,
	_Out_	PVOID 			OutputBuffer,
	_In_	UINT 			OutputBufferLength
)
{...}

typedef EVT_NET_REQUEST_QUERY_DATA *PFN_NET_REQUEST_QUERY_DATA;
```

## -parameters

### -param RequestQueue 
A handle to a net request queue object.

### -param Request 
A handle to a network request object.

### -param OutputBuffer 
A pointer to a caller-supplied buffer.

### -param OutputBufferLength 
The length, in bytes, of the request's output buffer, if an output buffer is available.

## -returns

This callback function does not return a value.

## -remarks
To register an *EVT_NET_REQUEST_QUERY_DATA* callback function, the client driver calls [NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_query_data_handler.md) or [NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_initialized_query_data_handler.md), and then calls [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

Your client driver can provide one or more specialized handlers for specific OID query requests. In addition, it can also provide a generic *[EVT_NET_REQUEST_DEFAULT_QUERY_DATA](nc-netrequestqueue-evt_net_request_default_query_data.md)* callback function.



## -see-also
