---
UID: NC:netrequestqueue.EVT_NET_REQUEST_DEFAULT_METHOD
title: EVT_NET_REQUEST_DEFAULT_METHOD (netrequestqueue.h)
description: Implemented by the client driver as the default handler for method object identifier (OID) requests.
tech.root: netvista
ms.assetid: b9b871b2-b92a-47f1-9b68-ccfbca6eeeea
ms.date: 02/01/2019
ms.topic: callback
f1_keywords:
 - "netrequestqueue/NetRequestWdmGetNdisOidRequest"
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
- EVT_NET_REQUEST_DEFAULT_METHOD
targetos: Windows
product:
- Windows
---

# EVT_NET_REQUEST_DEFAULT_METHOD callback function

## -description



Implemented by the client driver as the default handler for method object identifier (OID) requests.

## -prototype

```c++
//Declaration

EVT_NET_REQUEST_DEFAULT_METHOD EvtNetRequestDefaultMethod; 

// Definition

VOID EvtNetRequestDefaultMethod 
(
	_In_	NETREQUESTQUEUE	RequestQueue,
	_In_	NETREQUEST 		Request,
	_In_	NDIS_OID 		Oid,
	_Out_	void * 			InputOutputBuffer,
	_In_	UINT 			InputBufferLength,
	_In_	UINT 			OutputBufferLength
)
{...}

typedef EVT_NET_REQUEST_DEFAULT_METHOD *PFN_NET_REQUEST_DEFAULT_METHOD;
```

## -parameters

### -param RequestQueue 
A handle to a net request queue object.

### -param Request 
A handle to a network request object.

### -param Oid 
The object identifier of the requested operation. The value is an OID\_*XXX* code.

### -param InputOutputBuffer 
A pointer to a buffer into which the client driver or NetAdapterCx returns information for the specified request.

### -param InputBufferLength 
The length, in bytes, of the request's input buffer, if an input buffer is available.

### -param OutputBufferLength 
The length, in bytes, of the request's output buffer, if an output buffer is available.

## -remarks
Register your implementation of this callback function by setting the appropriate member of [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) and then calling [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

NetAdapterCx calls the client driver's *EVT_NET_REQUEST_DEFAULT_METHOD* handler when it receives an OID method request for which the client driver has not provided a specialized *[EVT_NET_REQUEST_METHOD](nc-netrequestqueue-evt_net_request_method.md)* handler.



## -see-also
