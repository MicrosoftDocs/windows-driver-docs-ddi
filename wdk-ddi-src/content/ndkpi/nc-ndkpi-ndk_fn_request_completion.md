---
UID: NC:ndkpi.NDK_FN_REQUEST_COMPLETION
title: NDK_FN_REQUEST_COMPLETION
author: windows-driver-content
description: The NdkRequestCompletion (NDK_FN_REQUEST_COMPLETION) function completes a pending NDK request.
old-location: netvista\ndk_fn_request_completion.htm
old-project: netvista
ms.assetid: EB507DE2-354C-41D2-9BEE-091C4AE299EC
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_request_completion, NdkRequestCompletion callback function [Network Drivers Starting with Windows Vista], NdkRequestCompletion, NDK_FN_REQUEST_COMPLETION, NDK_FN_REQUEST_COMPLETION, ndkpi/NdkRequestCompletion
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
-	NdkRequestCompletion
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_REQUEST_COMPLETION callback


## -description


The <i>NdkRequestCompletion</i> (<i>NDK_FN_REQUEST_COMPLETION</i>) function completes a pending NDK request.


## -prototype


````
NDK_FN_REQUEST_COMPLETION NdkRequestCompletion;

VOID NdkRequestCompletion(
  _In_opt_ PVOID    Context,
  _In_     NTSTATUS Status
)
{ ... }
````


## -parameters




#### - Context [in, optional]

The context value passed to the NDK provider when a consumer calls an asynchronous request function. The asynchronous request function  provides the context with the with the <i>NdkRequestCompletion</i> (<i>NDK_FN_REQUEST_COMPLETION</i>) function pointer.


#### - Status [in]

The asynchronous completion status for the request. See the asynchronous request  functions (for example, <a href="..\ndkpi\nc-ndkpi-ndk_fn_accept.md">NDK_FN_ACCEPT</a>) for completion status codes that can be returned for each type of request.


## -returns


None



## -remarks


Many NDK requests can be completed asynchronously. Asynchronous request functions require the consumer to pass an <i>NDK_FN_REQUEST_COMPLETION</i> function pointer as an input. If an asynchronous request function returns STATUS_PENDING, the provider must call the <i>NdkRequestCompletion</i> (<i>NDK_FN_REQUEST_COMPLETION</i>)  function to indicate completion of the request. If an asynchronous request functions returns anything other than STATUS_PENDING,   the request was handled immediately and the provider must not call <i>NdkRequestCompletion</i>.



## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_accept.md">NDK_FN_ACCEPT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_REQUEST_COMPLETION callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

