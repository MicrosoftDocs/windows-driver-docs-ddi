---
UID: NC:ndkpi.NDK_FN_DISCONNECT
title: NDK_FN_DISCONNECT (ndkpi.h)
description: The NdkDisconnect (NDK_FN_DISCONNECT) function starts a disconnect on an NDK connection.
old-location: netvista\ndk_fn_disconnect.htm
tech.root: netvista
ms.assetid: 40622358-F4CA-4DF2-BDA4-E93C4DDB1AF6
ms.date: 05/02/2018
keywords: ["NDK_FN_DISCONNECT callback function"]
ms.keywords: NDK_FN_DISCONNECT, NDK_FN_DISCONNECT callback, NdkDisconnect, NdkDisconnect callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkDisconnect, netvista.ndk_fn_disconnect
f1_keywords:
 - "ndkpi/NdkDisconnect"
 - "NdkDisconnect"
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
- NdkDisconnect
targetos: Windows
req.typenames: 
---

# NDK_FN_DISCONNECT callback function


## -description


The <i>NdkDisconnect</i> (<i>NDK_FN_DISCONNECT</i>) function starts a  disconnect on an NDK connection.


## -parameters




### -param pNdkConnector 
[in]
A pointer to a connector object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>).


### -param RequestCompletion 
[in]
A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext 
[in, optional]
A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


## -returns



The <i>NdkDisconnect</i> function returns one of the following NTSTATUS codes.

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
The disconnect request was completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The disconnect handshake timed out. 

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



<i>NdkDisconnect</i> initiates a graceful disconnect on a connection. After the underlying protocol driver performs a graceful disconnect, the NDK provider must also perform an implicit flush on the QP.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect">NDK_FN_CONNECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>
 

 

