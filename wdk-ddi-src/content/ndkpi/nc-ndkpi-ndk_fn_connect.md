---
UID: NC:ndkpi.NDK_FN_CONNECT
title: NDK_FN_CONNECT
author: windows-driver-content
description: The NdkConnect (NDK_FN_CONNECT) function initiates an NDK connect request.
old-location: netvista\ndk_fn_connect.htm
old-project: netvista
ms.assetid: AFB291B7-7962-46D2-BB00-E1CB8B0BF5FC
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndk_fn_connect, NdkConnect callback function [Network Drivers Starting with Windows Vista], NdkConnect, NDK_FN_CONNECT, NDK_FN_CONNECT, ndkpi/NdkConnect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndkpi.h
apiname:
-	NdkConnect
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_CONNECT callback


## -description


The <i>NdkConnect</i> (<i>NDK_FN_CONNECT</i>) function initiates an NDK  connect request.


## -prototype


````
NDK_FN_CONNECT NdkConnect;

NTSTATUS NdkConnect(
  _In_     NDK_CONNECTOR                                       *pNdkConnector,
  _In_     NDK_QP                                              *pNdkQp,
           _In_reads_bytes_(SrcAddressLength) CONST PSOCKADDR  pSrcAddress,
  _In_     ULONG                                               SrcAddressLength,
           _In_reads_bytes_(DestAddressLength) CONST PSOCKADDR pDestAddress,
  _In_     ULONG                                               DestAddressLength,
  _In_     ULONG                                               InboundReadLimit,
  _In_     ULONG                                               OutboundReadLimit,
           _In_reads_bytes_opt_(PrivateDataLength) CONST PVOID pPrivateData,
  _In_     ULONG                                               PrivateDataLength,
  _In_     NDK_FN_REQUEST_COMPLETION                           RequestCompletion,
  _In_opt_ PVOID                                               RequestContext
)
{ ... }
````


## -parameters




### -param *pNdkConnector [in]

A pointer to an NDK connector object (<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>).


### -param *pNdkQp [in]

A pointer to an NDK queue pair (QP) object (<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>) to associate with the connection.


### -param PSOCKADDR


### -param SrcAddressLength [in]

The size, in bytes,  of source address data at the <i>pSrcAddress</i> parameter.


### -param DestAddressLength [in]

The size, in bytes,  of destination address data at the <i>pDestAddress</i> parameter.


### -param InboundReadLimit [in]

The consumer-supplied maximum number of incoming in-progress read operations to allow on the QP. If the underlying provider has a lower <b>MaxInboundReadLimit</b> value in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure, then the provider will cap the consumer-supplied value to the provider maximum. If the peer has a lower <i>OutboundReadLimit</i> value, then the provider will use that value as the effective <i>InboundReadLimit</i>. The consumer can retrieve the effective <i>InboundReadLimit</i> by calling the <i>NdkGetConnectionData</i> function (<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_connection_data.md">NDK_FN_GET_CONNECTION_DATA</a>).


### -param OutboundReadLimit [in]

The consumer-supplied maximum number of outgoing in-progress read operations to allow on the QP. If the underlying provider has a lower <b>MaxOutboundReadLimit</b> value  in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure, then the provider will cap the consumer supplied value to the provider maximum. If the peer has a lower <i>InboundReadLimit</i>, then the provider will use that value as the effective <i>OutboundReadLimit</i>. The     consumer can retrieve the effective <i>OutboundReadLimit</i> by calling the <i>NdkGetConnectionData</i> function (<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_connection_data.md">NDK_FN_GET_CONNECTION_DATA</a>).


### -param PVOID


### -param PrivateDataLength [in]

The length, in bytes, of the private data that is provided in the <i>pPrivateData</i> parameter.


### -param RequestCompletion [in]

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


#### - pSrcAddress

A source address.  For AF_INET or AF_INET6 <i>pSrcAddress</i>  is the source IP address and the source ND port.


#### - pDestAddress

A destination address.  For AF_INET or AF_INET6 <i>pDestAddress</i>  is the destination IP address and the source ND port .


#### - pPrivateData

A pointer to private data that is sent with the connect request.


## -returns



The 
     <i>NdkConnect</i> function returns one of the following NTSTATUS codes.

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
The connect request was completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The  request failed due to insufficient resources. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NETWORK_UNREACHABLE</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the remote network was not reachable. The connection attempt can be retried. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_HOST_UNREACHABLE</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the remote host system was not reachable. The connection attempt can be retried. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_REFUSED</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the remote system refused the connection request. This can be due to lack of listener, backlog limits, or the peer actively rejecting the connection request. The connection attempt can be retried. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the connection request timed out. The connection attempt may be retried. Timeout values are selected by Network Direct providers to match their respective network characteristics. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SHARING_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the specified local address is already in use. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_ADDRESS</b></dt>
</dl>
</td>
<td width="60%">
The request failed because  the specified local address is not a valid address for the adapter. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TOO_MANY_ADDRESSES</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the consumer specified a local port number of zero, and the Network Direct provider was unable to allocate a port from the ephemeral port space (ports 49152-65535).

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ADDRESS_ALREADY_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The request failed because a connection with the combination of local address, local port, remote address, and remote port already exists. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
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



<i>NdkConnect</i> initiates a connect request from a  local address to a remote address.




## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_disconnect.md">NDK_FN_DISCONNECT</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_connector_dispatch.md">NDK_CONNECTOR_DISPATCH</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_connection_data.md">NDK_FN_GET_CONNECTION_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CONNECT callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

