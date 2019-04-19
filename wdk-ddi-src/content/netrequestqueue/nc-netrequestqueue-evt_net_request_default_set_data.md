---
UID: NC:netrequestqueue.EVT_NET_REQUEST_DEFAULT_SET_DATA
title: EVT_NET_REQUEST_DEFAULT_SET_DATA (netrequestqueue.h)
description: Implemented by the client driver as the default handler for set object identifier (OID) requests.
tech.root: netvista
ms.assetid: 28db8bbf-199f-4724-a6a0-3a31a8e71313
ms.date: 02/01/2019
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
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	netrequestqueue.h
apiname: 
-	EVT_NET_REQUEST_DEFAULT_SET_DATA
product:
- Windows
targetos: Windows
product:
- Windows
---

# EVT_NET_REQUEST_DEFAULT_SET_DATA callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Implemented by the client driver as the default handler for set object identifier (OID) requests.

## -prototype

```c++
//Declaration

EVT_NET_REQUEST_DEFAULT_SET_DATA EvtNetRequestDefaultSetData; 

// Definition

VOID EvtNetRequestDefaultSetData 
(
	_In_	NETREQUESTQUEUE	RequestQueue,
	_In_	NETREQUEST		Request,
	_In_	NDIS_OID		Oid,
	_In_	void *			InputBuffer,
	_In_	UINT			InputBufferLength
)
{...}

typedef EVT_NET_REQUEST_DEFAULT_SET_DATA *PFN_NET_REQUEST_DEFAULT_SET_DATA;
```

## -parameters

### -param RequestQueue 
A handle to a net request queue object.

### -param Request 
A handle to a net request object.

### -param Oid 
Specifies the object identifier of the requested operation. The value is an OID\_*XXX* code. 

### -param InputBuffer 
A pointer to a caller-supplied buffer.

### -param InputBufferLength 
The size of the buffer pointed to by *InputBuffer*.

## -returns

This callback function does not return a value.

## -remarks
Register your implementation of this callback function by setting the appropriate member of [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) and then calling [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

NetAdapterCx calls the client driver's *EVT_NET_REQUEST_DEFAULT_SET_DATA* handler when it receives an OID set data request for which the client driver has not provided a specialized *[EVT_NET_REQUEST_SET_DATA](nc-netrequestqueue-evt_net_request_set_data.md)* handler.



## -see-also
