---
UID: NC:ndkpi.NDK_FN_CREATE_COMPLETION
title: NDK_FN_CREATE_COMPLETION
author: windows-driver-content
description: The NdkCreateCompletion (NDK_FN_CREATE_COMPLETION) function completes the creation of an NDK object.
old-location: netvista\ndk_fn_create_completion.htm
old-project: netvista
ms.assetid: C7A2792C-FDAE-4525-A8B1-7F8F6BA8249A
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDK_FN_CREATE_COMPLETION, NdkCreateCompletion, NdkCreateCompletion callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCreateCompletion, netvista.ndk_fn_create_completion
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndkpi.h
api_name:
-	NdkCreateCompletion
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_CREATE_COMPLETION callback


## -description


The <i>NdkCreateCompletion</i> (<i>NDK_FN_CREATE_COMPLETION</i>) function completes the creation of an NDK object.


## -parameters




### -param Context [in, optional]

The context value passed to the NDK provider when a consumer calls an object creation function. The creation function  provides the context with the asynchronous create completion request <i>NdkCreateCompletion</i> (<i>NDK_FN_CREATE_COMPLETION</i>) function pointer.


### -param Status [in]

The asynchronous completion status for the create request. See the object creation functions (for example, <a href="https://msdn.microsoft.com/library/windows/hardware/hh439873">NDK_FN_CREATE_CQ</a>) for completion status codes that can be returned for each type of object.


### -param *pNdkObject [in]

A pointer to an NDK object header (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>).


## -returns



None




## -remarks



<div class="alert"><b>Note</b>  This function is implemented by the NDK consumer and passed to the NDK provider.</div>
<div> </div>
NDK objects are created with asynchronous functions. These asynchronous object creation functions take an <i>NDK_FN_CREATE_COMPLETION</i> function pointer as an input parameter. 

An NDK provider can return STATUS_PENDING from an asynchronous object creation function. In this case, the  NDK provider must call the create completion function to indicate that the object creation is complete. 

Any status other status code indicates inline completion. In this case, the provider must not call the create request completion function. If the create request function returns an NT_STATUS status code other than STATUS_PENDING, the created object must be returned in an output parameter with the create request function. 

For create requests that return STATUS_PENDING and later complete with STATUS_SUCCESS asynchronously, the created object must be returned by the create completion function with the <i>pNdkObject</i> parameter and the provider must not access the object output parameter of the create request function.




## -see-also




<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439872">NDK_FN_CREATE_CONNECTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439873">NDK_FN_CREATE_CQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439874">NDK_FN_CREATE_LISTENER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439875">NDK_FN_CREATE_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439876">NDK_FN_CREATE_MW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439877">NDK_FN_CREATE_PD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439878">NDK_FN_CREATE_QP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439880">NDK_FN_CREATE_QP_WITH_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439882">NDK_FN_CREATE_SHARED_ENDPOINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439883">NDK_FN_CREATE_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>
 

 

