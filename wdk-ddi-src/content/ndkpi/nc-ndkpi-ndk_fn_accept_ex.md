---
UID: NC:ndkpi.NDK_FN_ACCEPT_EX
title: NDK_FN_ACCEPT_EX
ms.date: 12/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdkAcceptEx (NDK_FN_ACCEPT_EX) function accepts an incoming connection request over a listener object.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndkpi.h
req.idl: 
req.include-header: Ndkpi.h
req.irql: <=DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDKPI 2.1 and later.
req.target-min-winversvr: 
req.target-type: Windows
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - ndkpi.h
api_name:
 - NDK_FN_ACCEPT_EX
f1_keywords:
 - NDK_FN_ACCEPT_EX
 - ndkpi/NDK_FN_ACCEPT_EX
dev_langs:
 - c++
---

## -description

The *NdkAcceptEx* (*NDK_FN_ACCEPT_EX*) function accepts an incoming connection request over a listener object.

## -parameters

### -param pNdkConnector 

[in]
A pointer to an NDK connector object ([NDK_CONNECTOR](/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector)).

### -param pNdkQp 

[in]
A pointer to an NDK queue pair (QP) object ([NDK_QP](/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp)) to associate with the connection.

### -param InboundReadLimit 

[in]
The consumer-supplied maximum number of incoming in-progress read operations to allow on the QP. If the underlying provider has a lower **MaxInboundReadLimit** value in the [NDK_ADAPTER_INFO](/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info) structure, then the provider will cap the consumer-supplied value to the provider maximum. If the peer has a lower *OutboundReadLimit* value, then the provider will use that value as the effective *InboundReadLimit*. The consumer can retrieve the effective *InboundReadLimit* by calling the *NdkGetConnectionData* function ([NDK_FN_GET_CONNECTION_DATA](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_connection_data)).

### -param OutboundReadLimit 

[in]
The consumer-supplied maximum number of outgoing in-progress read operations to allow on the QP. If the underlying provider has a lower **MaxOutboundReadLimit** value  in the [NDK_ADAPTER_INFO](/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info) structure, then the provider will cap the consumer supplied value to the provider maximum. If the peer has a lower *InboundReadLimit*, then the provider will use that value as the effective *OutboundReadLimit*. The consumer can retrieve the effective *OutboundReadLimit* by calling the *NdkGetConnectionData* function ([NDK_FN_GET_CONNECTION_DATA](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_connection_data)).

### -param PVOID

### -param PrivateDataLength 

[in]
The length, in bytes, of the private data that is provided in the *pPrivateData* parameter.

### -param DisconnectEvent

[in, optional]
An entry point for an optional disconnect notification callback function NdkDisconnectEventCallbackEx [NDK_FN_DISCONNECT_EVENT_CALLBACK_EX](nc-ndkpi-ndk_fn_disconnect_event_callback_ex.md). The provider calls this callback function when the peer disconnects.

### -param DisconnectEventContext 

[in, optional]
A context value to pass to the *DisconnectEventContext* parameter of the  callback function that is specified in the *DisconnectEvent* parameter.

### -param RequestCompletion 

[in]
A pointer to a request completion callback routine *NdkRequestCompletion* ([NDK_FN_REQUEST_COMPLETION](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion)).

### -param RequestContext 

[in, optional]
A context value to pass to the *Context* parameter of the  callback function that is specified in the *RequestCompletion* parameter.

## -returns

The *NDK_FN_ACCEPT_EX* function returns one of the following NTSTATUS codes.

|Return code|Description|
|--- |--- |
|**STATUS_SUCCESS**|The operation completed successfully.|
|**STATUS_PENDING**|The operation is pending and will be completed later. The driver will call the specified _RequestCompletion_ ([NDK_FN_REQUEST_COMPLETION](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion)) function to complete the pending operation.|
|**STATUS_CONNECTION_ABORTED**|The connecting peer abandoned the pending connection establishment.|
|**STATUS_IO_TIMEOUT**|The peer did not call the CompleteConnect ([NDK_FN_COMPLETE_CONNECT_EX](nc-ndkpi-ndk_fn_complete_connect_ex.md)) function to complete the pending connection request.|
|**Other status codes**|An error occurred.|


## -remarks

The NDK consumer calls *NdkAcceptEx* to accept an incoming connection request over a listener object.

The *NdkCreateListener* ([NDK_FN_CREATE_LISTENER](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener)) function creates an NDK listener object and provides an *NdkConnectEventCallback* function ([NDK_FN_CONNECT_EVENT_CALLBACK](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect_event_callback)).

The *NdkFnConnectEventCallback* function is used by the NDK provider to notify the consumer about each incoming connection request.

## -see-also

[NDK_FN_DISCONNECT_EVENT_CALLBACK_EX](nc-ndkpi-ndk_fn_disconnect_event_callback_ex.md)

[NDK_FN_COMPLETE_CONNECT_EX](nc-ndkpi-ndk_fn_complete_connect_ex.md)

[NDKPI Object Lifetime Requirements](/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements)



[NDK_ADAPTER_INFO](/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info)



[NDK_CONNECTOR](/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector)



[NDK_CONNECTOR_DISPATCH](/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch)



[NDK_FN_CONNECT_EVENT_CALLBACK](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect_event_callback)



[NDK_FN_CREATE_LISTENER](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener)



[NDK_FN_GET_CONNECTION_DATA](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_connection_data)



[NDK_FN_REJECT](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_reject)



[NDK_FN_REQUEST_COMPLETION](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion)



[NDK_QP](/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp)