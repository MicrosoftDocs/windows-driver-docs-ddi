---
UID: NC:netrequestqueue.EVT_NET_REQUEST_DEFAULT
title: EVT_NET_REQUEST_DEFAULT (netrequestqueue.h)
description: Implemented by the client driver as the default handler for object identifier (OID) requests that are not query, set, or method requests.
tech.root: netvista
ms.assetid: 8ccfb961-9677-40a3-8ab5-4d450dfb3e46
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location:
- netrequestqueue.h
api_name: 
- EVT_NET_REQUEST_DEFAULT
product:
- Windows
targetos: Windows
product:
- Windows
---

# EVT_NET_REQUEST_DEFAULT callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Implemented by the client driver as the default handler for object identifier (OID) requests that are not query, set, or method requests.

## -prototype

```c++
//Declaration

EVT_NET_REQUEST_DEFAULT EvtNetRequestDefault; 

// Definition

VOID EvtNetRequestDefault 
(
	_In_	NETREQUESTQUEUE		RequestQueue,
	_In_	NETREQUEST			Request,
	_In_	NDIS_REQUEST_TYPE	RequestType,
	_In_	NDIS_OID			Oid,
	_Inout_	PVOID				InputOutputBuffer,
	_In_	UINT				InputBufferLength,
	_In_	UINT				OutputBufferLength
)
{...}

typedef EVT_NET_REQUEST_DEFAULT *PFN_NET_REQUEST_DEFAULT;
```

## -parameters

### -param RequestQueue 
A handle to the net request queue object that is associated with the I/O request.

### -param Request 
A handle to a network request object.

### -param RequestType 
The request type as one of the [NDIS_REQUEST_TYPE](../ntddndis/ne-ntddndis-_ndis_request_type.md) enumeration values.

### -param Oid 
The object identifier of the requested operation. The value is an OID\_*XXX* code.

### -param InputOutputBuffer 
A pointer to a buffer into which the client driver or NetAdapterCx returns information for the specified request.

### -param InputBufferLength 
The length, in bytes, of the request's input buffer, if an input buffer is available.

### -param OutputBufferLength 
The length, in bytes, of the request's output buffer, if an output buffer is available.

## -returns

This callback function does not return a value.

## -remarks
Register your implementation of this callback function by setting the appropriate member of [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) and then calling [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

If NDIS_REQUEST_TYPE is not query, set, or method, NetAdapterCx calls the client driver's *EVT_NET_REQUEST_DEFAULT* handler with the request. If the client driver has not provided this callback, the request fails.

The contents of the *InputOutputBuffer*, *InputBufferLength*, and *OutputBufferLength* parameters are specific to NDIS_REQUEST_TYPE.



## -see-also

[MiniportOidRequest](../ndis/nc-ndis-miniport_oid_request.md)

[NDIS_OID_REQUEST](../ndis/ns-ndis-_ndis_oid_request.md)
