---
UID: NC:ndkpi.NDK_FN_CLOSE_COMPLETION
title: NDK_FN_CLOSE_COMPLETION (ndkpi.h)
description: The NdkCloseCompletion (NDK_FN_CLOSE_COMPLETION) function is an asynchronous completion function for closing NDK objects.
old-location: netvista\ndk_fn_close_completion.htm
tech.root: netvista
ms.assetid: EB3C395F-235A-4B9A-B777-E4E8CD8AFC3C
ms.date: 05/02/2018
ms.keywords: NDK_FN_CLOSE_COMPLETION, NDK_FN_CLOSE_COMPLETION callback, NdkCloseCompletion, NdkCloseCompletion callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCloseCompletion, netvista.ndk_fn_close_completion
ms.topic: callback
f1_keywords:
 - "ndkpi/NdkCloseCompletion"
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
- NdkCloseCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_CLOSE_COMPLETION callback function


## -description


 The <i>NdkCloseCompletion</i> (<i>NDK_FN_CLOSE_COMPLETION</i>) function is an asynchronous completion function for closing NDK objects.


## -parameters




### -param Context [in, optional]

A context value for each close request that is passed to the provider with the  asynchronous close request function (<i>NDK_FN_CLOSE_COMPLETION</i>)  pointer.


## -remarks



<div class="alert"><b>Note</b>  This function is implemented by the NDK consumer and passed to the NDK provider.</div>
<div> </div>
The NDK programming interface includes an  <i>NdkCloseObject</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>) function for NDK objects. For more information about NDK objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ne-ndkpi-_ndk_object_type">NDK_OBJECT_TYPE</a>.

 NDK close requests can return either STATUS_SUCCESS or STATUS_PENDING. That is, a close request can never fail, but can be completed asynchronously at a later time. The provider must call the <i>NdkCloseCompletion</i> function if  <i>NdkCloseObject</i> returns STATUS_PENDING. The provider must not call the <i>NdkCloseCompletion</i> function if the <i>NdkCloseCompletion</i> function returns any status other than STATUS_PENDING.

A close request will remain pending while there is another pending request or an in-progress notification callback on the object being closed.

The provider will call the <i>NdkCloseCompletion</i> function after all  pending requests have been completed for the object (that is, the provider called the associated completion function for a request and the completion function returned control back to the provider) and all in-progress notification callbacks have returned control back to the provider.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ne-ndkpi-_ndk_object_type">NDK_OBJECT_TYPE</a>
 

 

