---
UID: NC:netrequestqueue.EVT_NET_REQUEST_SET_DATA
title: EVT_NET_REQUEST_SET_DATA (netrequestqueue.h)
description: Implemented by the client driver to handle a specific OID set request.
tech.root: netvista
ms.assetid: 213e6c64-701e-42ce-9e0e-7c8849dcedd6
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
-	EVT_NET_REQUEST_SET_DATA
product:
-	Windows
targetos: Windows
product:
- Windows
---

# EVT_NET_REQUEST_SET_DATA callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Implemented by the client driver to handle a specific OID set request.

## -prototype

```c++
//Declaration

EVT_NET_REQUEST_SET_DATA EvtNetRequestSetData; 

// Definition

VOID EvtNetRequestSetData 
(
	_In_	NETREQUESTQUEUE	RequestQueue,
	_In_	NETREQUEST 		Request,
	_In_	void * 			InputBuffer,
	_In_	UINT 			InputBufferLength
)
{...}

typedef EVT_NET_REQUEST_SET_DATA *PFN_NET_REQUEST_SET_DATA;
```

## -parameters

### -param RequestQueue 
A handle to a net request queue object.

### -param Request 
A handle to a network request object.

### -param InputBuffer 
A pointer to a caller-supplied buffer.

### -param InputBufferLength 
The length, in bytes, of the request's input buffer, if an input buffer is available.

## -returns

This callback function does not return a value.

## -remarks
To register an *EVT_NET_REQUEST_SET_DATA* callback function, the client driver calls [NET_REQUEST_QUEUE_CONFIG_ADD_SET_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_set_data_handler.md) or [NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_SET_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_initialized_set_data_handler.md), and then calls [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

Your client driver can provide one or more specialized handlers for specific OID set requests. In addition, it can also provide a generic *[EVT_NET_REQUEST_DEFAULT_SET_DATA](nc-netrequestqueue-evt_net_request_default_set_data.md)* callback function.



## -see-also
