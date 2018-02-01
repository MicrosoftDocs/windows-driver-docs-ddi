---
UID: NC:ndkpi.NDK_FN_LISTEN
title: NDK_FN_LISTEN
author: windows-driver-content
description: The NdkListen (NDK_FN_LISTEN) function puts an NDK listener object into listening mode.
old-location: netvista\ndk_fn_listen.htm
old-project: netvista
ms.assetid: 1C3DF31C-500E-456A-B121-48F5945D6999
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_listen, NdkListen callback function [Network Drivers Starting with Windows Vista], NdkListen, NDK_FN_LISTEN, NDK_FN_LISTEN, ndkpi/NdkListen
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
-	NdkListen
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_LISTEN callback


## -description


The <i>NdkListen</i> (<i>NDK_FN_LISTEN</i>) function puts an NDK listener object into listening mode.


## -prototype


````
NDK_FN_LISTEN NdkListen;

NTSTATUS NdkListen(
  _In_     NDK_LISTENER                                    *pNdkListener,
           _In_reads_bytes_(AddressLength) const PSOCKADDR pAddress,
  _In_     ULONG                                           AddressLength,
  _In_     NDK_FN_REQUEST_COMPLETION                       RequestCompletion,
  _In_opt_ PVOID                                           RequestContext
)
{ ... }
````


## -parameters




### -param *pNdkListener [in]

A pointer to an NDK listener object (<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>).


### -param PSOCKADDR



### -param AddressLength [in]

The size, in bytes, of local address data at the <i>pAddress</i> parameter.




### -param RequestCompletion [in]

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


#### - pAddress

A local address to listen on. For AF_INET or AF_INET6 <i>pAddress</i> contains the local IP address and local ND port.




## -returns


The 
     <i>NdkListen</i> function returns one of the following NTSTATUS codes.
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
The listen request succeeded.


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
The request failed due to insufficient resources. 

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
	The request failed because the specified local address is not a valid address for the adapter. 

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
The request failed because the consumer specified a local port number of zero, and the Network Direct provider was unable to allocate a port from the ephemeral port space (ports 49152-65535.)

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


<i>NdkListen</i> puts a listener object into listening mode on the specified  local address.



## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>

<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_LISTEN callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

