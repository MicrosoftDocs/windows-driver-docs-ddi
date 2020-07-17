---
UID: NC:netrequestqueue.EVT_NET_REQUEST_METHOD
title: EVT_NET_REQUEST_METHOD (netrequestqueue.h)
description: Implemented by the client driver to handle a specific method OID request.
tech.root: netvista
ms.assetid: c9df356a-9b50-4906-aa8f-20b81e0dacb2
ms.date: 02/08/2018
keywords: ["EVT_NET_REQUEST_METHOD callback function"]
f1_keywords:
 - "netrequestqueue/NetRequestWdmGetNdisOidRequest"
 - "NetRequestWdmGetNdisOidRequest"
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
- EVT_NET_REQUEST_METHOD
targetos: Windows
product:
- Windows
---

# EVT_NET_REQUEST_METHOD callback function

## -description



Implemented by the client driver to handle a specific method OID request.

## -prototype

```c++
//Declaration

EVT_NET_REQUEST_METHOD EvtNetRequestMethod; 

// Definition

VOID EvtNetRequestMethod 
(
	_In_	NETREQUESTQUEUE	RequestQueue,
	_In_	NETREQUEST		Request,
	_Out_	void *			InputOutputBuffer,
	_In_	UINT			InputBufferLength,
	_In_	UINT			OutputBufferLength
)
{...}

typedef EVT_NET_REQUEST_METHOD *PFN_NET_REQUEST_METHOD;
```

## -parameters

### -param RequestQueue 
A handle to a net request queue object.

### -param Request 
A handle to a network request object.

### -param InputOutputBuffer 
A pointer to a buffer into which the client driver or NetAdapterCx returns information for the specified request.

### -param InputBufferLength 
The length, in bytes, of the request's input buffer, if an input buffer is available.

### -param OutputBufferLength 
The length, in bytes, of the request's output buffer, if an output buffer is available.

## -remarks
To register an *EVT_NET_REQUEST_METHOD* callback function, the client driver calls [NET_REQUEST_QUEUE_CONFIG_ADD_METHOD_HANDLER](nf-netrequestqueue-net_request_queue_config_add_method_handler.md) or [NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_METHOD_HANDLER](nf-netrequestqueue-net_request_queue_config_add_initialized_method_handler.md), and then calls [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

Your client driver can provide one or more specialized handlers for specific OID method requests. In addition, it can also provide a generic *[EVT_NET_REQUEST_DEFAULT_METHOD](nc-netrequestqueue-evt_net_request_default_method.md)* callback function.



## -see-also
