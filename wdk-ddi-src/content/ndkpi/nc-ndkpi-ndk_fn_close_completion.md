---
UID: NC:ndkpi.NDK_FN_CLOSE_COMPLETION
title: NDK_FN_CLOSE_COMPLETION
author: windows-driver-content
description: The NdkCloseCompletion (NDK_FN_CLOSE_COMPLETION) function is an asynchronous completion function for closing NDK objects.
old-location: netvista\ndk_fn_close_completion.htm
old-project: netvista
ms.assetid: EB3C395F-235A-4B9A-B777-E4E8CD8AFC3C
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_close_completion, NdkCloseCompletion callback function [Network Drivers Starting with Windows Vista], NdkCloseCompletion, NDK_FN_CLOSE_COMPLETION, NDK_FN_CLOSE_COMPLETION, ndkpi/NdkCloseCompletion
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
-	NdkCloseCompletion
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_CLOSE_COMPLETION callback


## -description


 The <i>NdkCloseCompletion</i> (<i>NDK_FN_CLOSE_COMPLETION</i>) function is an asynchronous completion function for closing NDK objects.


## -prototype


````
NDK_FN_CLOSE_COMPLETION NdkCloseCompletion;

VOID NdkCloseCompletion(
  _In_opt_ PVOID Context
)
{ ... }
````


## -parameters




### -param Context [in, optional]

A context value for each close request that is passed to the provider with the  asynchronous close request function (<i>NDK_FN_CLOSE_COMPLETION</i>)  pointer.


## -returns


None



## -remarks


<div class="alert"><b>Note</b>  This function is implemented by the NDK consumer and passed to the NDK provider.</div><div> </div>The NDK programming interface includes an  <i>NdkCloseObject</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>) function for NDK objects. For more information about NDK objects, see <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> and <a href="..\ndkpi\ne-ndkpi-_ndk_object_type.md">NDK_OBJECT_TYPE</a>.

 NDK close requests can return either STATUS_SUCCESS or STATUS_PENDING. That is, a close request can never fail, but can be completed asynchronously at a later time. The provider must call the <i>NdkCloseCompletion</i> function if  <i>NdkCloseObject</i> returns STATUS_PENDING. The provider must not call the <i>NdkCloseCompletion</i> function if the <i>NdkCloseCompletion</i> function returns any status other than STATUS_PENDING.

A close request will remain pending while there is another pending request or an in-progress notification callback on the object being closed.

The provider will call the <i>NdkCloseCompletion</i> function after all  pending requests have been completed for the object (that is, the provider called the associated completion function for a request and the completion function returned control back to the provider) and all in-progress notification callbacks have returned control back to the provider.



## -see-also

<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>

<a href="..\ndkpi\ne-ndkpi-_ndk_object_type.md">NDK_OBJECT_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CLOSE_COMPLETION callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

