---
UID: NC:ndkpi.NDK_FN_REQUEST_COMPLETION
title: NDK_FN_REQUEST_COMPLETION (ndkpi.h)
description: The NdkRequestCompletion (NDK_FN_REQUEST_COMPLETION) function completes a pending NDK request.
old-location: netvista\ndk_fn_request_completion.htm
tech.root: netvista
ms.assetid: EB507DE2-354C-41D2-9BEE-091C4AE299EC
ms.date: 05/02/2018
ms.keywords: NDK_FN_REQUEST_COMPLETION, NDK_FN_REQUEST_COMPLETION callback, NdkRequestCompletion, NdkRequestCompletion callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkRequestCompletion, netvista.ndk_fn_request_completion
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndkpi.h
api_name:
- NdkRequestCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_REQUEST_COMPLETION callback function


## -description


The <i>NdkRequestCompletion</i> (<i>NDK_FN_REQUEST_COMPLETION</i>) function completes a pending NDK request.


## -parameters




### -param Context [in, optional]

The context value passed to the NDK provider when a consumer calls an asynchronous request function. The asynchronous request function  provides the context with the with the <i>NdkRequestCompletion</i> (<i>NDK_FN_REQUEST_COMPLETION</i>) function pointer.


### -param Status [in]

The asynchronous completion status for the request. See the asynchronous request  functions (for example, <a href="https://msdn.microsoft.com/library/windows/hardware/hh439857">NDK_FN_ACCEPT</a>) for completion status codes that can be returned for each type of request.


## -returns



None




## -remarks



Many NDK requests can be completed asynchronously. Asynchronous request functions require the consumer to pass an <i>NDK_FN_REQUEST_COMPLETION</i> function pointer as an input. If an asynchronous request function returns STATUS_PENDING, the provider must call the <i>NdkRequestCompletion</i> (<i>NDK_FN_REQUEST_COMPLETION</i>)  function to indicate completion of the request. If an asynchronous request functions returns anything other than STATUS_PENDING,   the request was handled immediately and the provider must not call <i>NdkRequestCompletion</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439857">NDK_FN_ACCEPT</a>
 

 

