---
UID: NC:ndkpi.NDK_FN_COMPLETE_CONNECT
title: NDK_FN_COMPLETE_CONNECT
author: windows-driver-content
description: The NdkCompleteConnect (NDK_FN_COMPLETE_CONNECT) function completes an asynchronous connection request.
old-location: netvista\ndk_fn_complete_connect.htm
old-project: netvista
ms.assetid: 85AD83CE-C00F-4D5A-BCDE-22D1B83201A8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_complete_connect, NdkCompleteConnect callback function [Network Drivers Starting with Windows Vista], NdkCompleteConnect, NDK_FN_COMPLETE_CONNECT, NDK_FN_COMPLETE_CONNECT, ndkpi/NdkCompleteConnect
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
-	NdkCompleteConnect
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS"
---

# NDK_FN_COMPLETE_CONNECT callback


## -description


The <i>NdkCompleteConnect</i> (<i>NDK_FN_COMPLETE_CONNECT</i>) function completes an asynchronous connection request.


## -prototype


````
NDK_FN_COMPLETE_CONNECT NdkCompleteConnect;

NTSTATUS NdkCompleteConnect(
  _In_     NDK_CONNECTOR                    *pNdkConnector,
  _In_opt_ NDK_FN_DISCONNECT_EVENT_CALLBACK DisconnectEvent,
  _In_opt_ PVOID                            DisconnectEventContext,
  _In_     NDK_FN_REQUEST_COMPLETION        RequestCompletion,
  _In_opt_ PVOID                            RequestContext
)
{ ... }
````


## -parameters




### -param *pNdkConnector [in]

A pointer to an NDK connector object (<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>).



### -param DisconnectEvent [in, optional]

An optional disconnect notification callback <i>NdkDisconnectEventCallback</i>  function(<a href="..\ndkpi\nc-ndkpi-ndk_fn_disconnect_event_callback.md">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>) that the provider calls when the peer disconnects.


### -param DisconnectEventContext [in, optional]

A context value to pass back to the <i>NdkDisconnectEventCallback</i> function that is specified in the  <i>DisconnectEvent</i> parameter.


### -param RequestCompletion [in]

A pointer to a request completion callback <i>NdkRequestCompletion</i>  function (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).


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



The <i>NdkCompleteConnect</i> function completes a connection request that was  initiated by a previous call to the <i>NdkConnect</i>  (<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect.md">NDK_FN_CONNECT</a>) function. The NDK consumer calls <i>NdkCompleteConnect</i> after the peer accepts the connection request.




## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_disconnect_event_callback.md">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect.md">NDK_FN_CONNECT</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_connector_dispatch.md">NDK_CONNECTOR_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_COMPLETE_CONNECT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

