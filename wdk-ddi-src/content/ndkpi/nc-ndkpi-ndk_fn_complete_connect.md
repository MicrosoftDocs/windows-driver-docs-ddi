---
UID: NC:ndkpi.NDK_FN_COMPLETE_CONNECT
title: NDK_FN_COMPLETE_CONNECT (ndkpi.h)
description: The NdkCompleteConnect (NDK_FN_COMPLETE_CONNECT) function completes an asynchronous connection request.
old-location: netvista\ndk_fn_complete_connect.htm
tech.root: netvista
ms.assetid: 85AD83CE-C00F-4D5A-BCDE-22D1B83201A8
ms.date: 05/02/2018
keywords: ["NDK_FN_COMPLETE_CONNECT callback function"]
ms.keywords: NDK_FN_COMPLETE_CONNECT, NDK_FN_COMPLETE_CONNECT callback, NdkCompleteConnect, NdkCompleteConnect callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCompleteConnect, netvista.ndk_fn_complete_connect
f1_keywords:
 - "ndkpi/NdkCompleteConnect"
 - "NdkCompleteConnect"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndkpi.h
api_name:
- NdkCompleteConnect
targetos: Windows
req.typenames: 
---

# NDK_FN_COMPLETE_CONNECT callback function


## -description


The <i>NdkCompleteConnect</i> (<i>NDK_FN_COMPLETE_CONNECT</i>) function completes an asynchronous connection request.


## -parameters




### -param pNdkConnector [in]

A pointer to an NDK connector object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>).



### -param DisconnectEvent [in, optional]

An optional disconnect notification callback <i>NdkDisconnectEventCallback</i>  function(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_disconnect_event_callback">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>) that the provider calls when the peer disconnects.


### -param DisconnectEventContext [in, optional]

A context value to pass back to the <i>NdkDisconnectEventCallback</i> function that is specified in the  <i>DisconnectEvent</i> parameter.


### -param RequestCompletion [in]

A pointer to a request completion callback <i>NdkRequestCompletion</i>  function (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value that  the provider passes back to the <i>NdkRequestCompletion</i> function that is specified in the <i>RequestCompletion</i> parameter.


## -returns



The 
     <i>NDK_FN_COMPLETE_CONNECT</i> function returns one of the following NTSTATUS codes.

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
The request was completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The request is pending. The provider will call the <i>NdkRequestCompletion</i> function that is specified in the <i>RequestCompletion</i> parameter  to complete the request asynchronously.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the queue pair is not connecting. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_ABORTED</b></dt>
</dl>
</td>
<td width="60%">
The accepting peer abandoned the pending connection establishment.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the connection establishment timed out. This is not an indication of a catastrophic or permanent failure, but it ends connection establishment for this connector.

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



The <i>NdkCompleteConnect</i> function completes a connection request that was  initiated by a previous call to the <i>NdkConnect</i>  (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect">NDK_FN_CONNECT</a>) function. The NDK consumer calls <i>NdkCompleteConnect</i> after the peer accepts the connection request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect">NDK_FN_CONNECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_disconnect_event_callback">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>
 

 

