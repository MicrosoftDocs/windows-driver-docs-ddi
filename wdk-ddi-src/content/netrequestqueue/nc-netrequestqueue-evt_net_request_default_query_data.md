---
UID: NC:netrequestqueue.EVT_NET_REQUEST_DEFAULT_QUERY_DATA
title: EVT_NET_REQUEST_DEFAULT_QUERY_DATA (netrequestqueue.h)
description: Implemented by the client driver as the default handler for query object identifier (OID) requests.
tech.root: netvista
ms.assetid: c3d390aa-d643-45a0-ab18-912724f6d7b6
ms.date: 02/01/2019
keywords: ["EVT_NET_REQUEST_DEFAULT_QUERY_DATA callback function"]
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
- EVT_NET_REQUEST_DEFAULT_QUERY_DATA
targetos: Windows
product:
- Windows
---

# EVT_NET_REQUEST_DEFAULT_QUERY_DATA callback function

## -description



Implemented by the client driver as the default handler for query object identifier (OID) requests.

## -prototype

```c++
//Declaration

EVT_NET_REQUEST_DEFAULT_QUERY_DATA EvtNetRequestDefaultQueryData; 

// Definition

VOID EvtNetRequestDefaultQueryData 
(
	_In_	NETREQUESTQUEUE	RequestQueue,
	_In_	NETREQUEST		Request,
	_In_	NDIS_OID		Oid,
	_Out_	void *			OutputBuffer,
	_In_	UINT			OutputBufferLength
)
{...}

typedef EVT_NET_REQUEST_DEFAULT_QUERY_DATA *PFN_NET_REQUEST_DEFAULT_QUERY_DATA;
```

## -parameters

### -param RequestQueue 
A handle to a net request queue object.

### -param Request 
A handle to a network request object.

### -param Oid 
The object identifier of the requested operation. The value is an OID_\*XXX* code.

### -param OutputBuffer 
A pointer to a caller-supplied buffer.

### -param OutputBufferLength 
The length, in bytes, of the request's output buffer, if an output buffer is available.

## -remarks
Register your implementation of this callback function by setting the appropriate member of [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) and then calling [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

NetAdapterCx calls the client driver's *EVT_NET_REQUEST_DEFAULT_QUERY_DATA* handler when it receives an OID query data request for which the client driver has not provided a specialized *[EVT_NET_REQUEST_QUERY_DATA](nc-netrequestqueue-evt_net_request_query_data.md)* handler.



## -see-also
