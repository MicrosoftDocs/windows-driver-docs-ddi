---
UID: NC:ndkpi.NDK_FN_ACCEPT
title: NDK_FN_ACCEPT (ndkpi.h)
description: The NdkAccept (NDK_FN_ACCEPT) function accepts an incoming connection request over a listener object.
old-location: netvista\ndk_fn_accept.htm
tech.root: netvista
ms.assetid: 1010F6AD-2D2F-46E5-816E-C5CE68ED11CF
ms.date: 05/02/2018
keywords: ["NDK_FN_ACCEPT callback function"]
ms.keywords: NDK_FN_ACCEPT, NDK_FN_ACCEPT callback, NdkAccept, NdkAccept callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkAccept, netvista.ndk_fn_accept
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NDK_FN_ACCEPT
 - ndkpi/NDK_FN_ACCEPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NdkAccept
---

# NDK_FN_ACCEPT callback function


## -description

The <i>NdkAccept</i> (<i>NDK_FN_ACCEPT</i>) function accepts  an incoming connection request over a listener object.

## -parameters

### -param pNdkConnector 

[in]
A pointer to an NDK connector object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>).

### -param pNdkQp 

[in]
A pointer to an NDK queue pair (QP) object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>) to associate with the connection.

### -param InboundReadLimit 

[in]
The consumer-supplied maximum number of incoming in-progress read operations to allow on the QP. If the underlying provider has a lower <b>MaxInboundReadLimit</b> value in the <a href="/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a> structure, then the provider will cap the consumer-supplied value to the provider maximum. If the peer has a lower <i>OutboundReadLimit</i> value, then the provider will use that value as the effective <i>InboundReadLimit</i>. The consumer can retrieve the effective <i>InboundReadLimit</i> by calling the <i>NdkGetConnectionData</i> function (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_connection_data">NDK_FN_GET_CONNECTION_DATA</a>).

### -param OutboundReadLimit 

[in]
The consumer-supplied maximum number of outgoing in-progress read operations to allow on the QP. If the underlying provider has a lower <b>MaxOutboundReadLimit</b> value  in the <a href="/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a> structure, then the provider will cap the consumer supplied value to the provider maximum. If the peer has a lower <i>InboundReadLimit</i>, then the provider will use that value as the effective <i>OutboundReadLimit</i>. The     consumer can retrieve the effective <i>OutboundReadLimit</i> by calling the <i>NdkGetConnectionData</i> function (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_connection_data">NDK_FN_GET_CONNECTION_DATA</a>).

### -param PVOID

### -param PrivateDataLength 

[in]
The length, in bytes, of the private data that is provided in the <i>pPrivateData</i> parameter.

### -param DisconnectEvent 

[in, optional]
An entry point for an optional disconnect notification callback function <i>NdkDisconnectEventCallback</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_disconnect_event_callback">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>). The provider calls this callback function when the peer disconnects.

### -param DisconnectEventContext 

[in, optional]
A context value to pass to the <i>DisconnectEventContext</i> parameter of the  callback function that is specified in the <i>DisconnectEvent</i> parameter.

### -param RequestCompletion 

[in]
A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>).

### -param RequestContext 

[in, optional]
A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


#### - pPrivateData

A pointer to private data that is sent back with the accept request.

## -returns

The 
     <i>NDK_FN_ACCEPT</i> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_ABORTED</b></dt>
</dl>
</td>
<td width="60%">
The connecting peer abandoned the pending connection establishment.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The peer did not call the CompleteConnect (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_complete_connect">NDK_FN_COMPLETE_CONNECT</a>) function to complete the pending connection request. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>

## -remarks

The  NDK consumer calls <i>NdkAccept</i> to accept  an incoming connection request over a listener object.

The <i>NdkCreateListener</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener">NDK_FN_CREATE_LISTENER</a>) function creates an NDK listener object and provides an <i>NdkConnectEventCallback</i> function (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect_event_callback">NDK_FN_CONNECT_EVENT_CALLBACK</a>).



The <i>NdkConnectEventCallback</i> function is used by the NDK provider to notify the consumer about each incoming connection request.

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_complete_connect">NDK_FN_COMPLETE_CONNECT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect_event_callback">NDK_FN_CONNECT_EVENT_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener">NDK_FN_CREATE_LISTENER</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_disconnect_event_callback">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_connection_data">NDK_FN_GET_CONNECTION_DATA</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_reject">NDK_FN_REJECT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>