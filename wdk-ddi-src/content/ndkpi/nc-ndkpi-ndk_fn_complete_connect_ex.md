---
UID: NC:ndkpi.NDK_FN_COMPLETE_CONNECT_EX
title: NDK_FN_COMPLETE_CONNECT_EX
ms.date: 12/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdkCompleteConnectEx (NDK_FN_COMPLETE_CONNECT_EX) function completes an asynchronous connection request.
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
req.target-min-winverclnt: Windows 10, version 21H1. Supported in NDKPI 2.1 and later.
req.target-min-winversvr: 
req.target-type: Windows
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
 - NDK_FN_COMPLETE_CONNECT_EX
f1_keywords:
 - NDK_FN_COMPLETE_CONNECT_EX
 - ndkpi/NDK_FN_COMPLETE_CONNECT_EX
dev_langs:
 - c++
---

## -description

The *NdkCompleteConnectEx* (*NDK_FN_COMPLETE_CONNECT_EX*) function completes an asynchronous connection request.

## -parameters

### -param pNdkConnector

[in]
A pointer to an NDK connector object ([NDK_CONNECTOR](/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector)).

### -param DisconnectEvent

[in, optional] 
An entry point for an optional disconnect notification callback function NdkDisconnectEventCallbackEx function [NDK_FN_DISCONNECT_EVENT_CALLBACK_EX](nc-ndkpi-ndk_fn_disconnect_event_callback_ex.md). The provider calls this callback function when the peer disconnects.

### -param DisconnectEventContext 

[in, optional]
A context value to pass back to the *NdkDisconnectEventCallback* function that is specified in the *DisconnectEvent* parameter.

### -param RequestCompletion 

[in]
A pointer to a request completion callback *NdkRequestCompletion* function ([NDK_FN_REQUEST_COMPLETION](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion)).

### -param RequestContext 

[in, optional]
A context value that the provider passes back to the *NdkRequestCompletion* function. This value is specified in the *RequestCompletion* parameter.

## -returns

The *NDK_FN_COMPLETE_CONNECT* function returns one of the following NTSTATUS codes.

|Return code|Description|
|--- |--- |
|**STATUS_SUCCESS**|The request was completed successfully.|
|**STATUS_PENDING**|The request is pending. The provider will call the _NdkRequestCompletion_ function that is specified in the _RequestCompletion_ parameter to complete the request asynchronously.|
|**STATUS_CONNECTION_INVALID**|The request failed because the queue pair is not connecting. **Important**: The request can fail inline as well as asynchronously with this status code.|
|**STATUS_CONNECTION_ABORTED**|The accepting peer abandoned the pending connection establishment.|
|**STATUS_IO_TIMEOUT**|The request failed because the connection establishment timed out. This is not an indication of a catastrophic or permanent failure, but it ends connection establishment for this connector. **Important**: The request can fail inline as well as asynchronously with this status code.|
|**Other status codes**|An error occurred.|

## -remarks

The *NdkCompleteConnectEx* function completes a connection request that was  initiated by a previous call to the *NdkConnect* ([NDK_FN_CONNECT](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect)) function. The NDK consumer calls *NdkCompleteConnectEx* after the peer accepts the connection request.

## -see-also

[NDK_FN_ACCEPT_EX](nc-ndkpi-ndk_fn_accept_ex.md)

[NDK_FN_DISCONNECT_EVENT_CALLBACK_EX](nc-ndkpi-ndk_fn_disconnect_event_callback_ex.md)

[NDKPI Object Lifetime Requirements](/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements)

[NDK_CONNECTOR](/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector)

[NDK_CONNECTOR_DISPATCH](/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch)



[NDK_FN_CONNECT](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect)



[NDK_FN_REQUEST_COMPLETION](/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion)