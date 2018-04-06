---
UID: NC:ndkpi.NDK_FN_CLOSE_OBJECT
title: NDK_FN_CLOSE_OBJECT
author: windows-driver-content
description: The NdkCloseObject (NDK_FN_CLOSE_OBJECT) function initiates a close request for an NDK object.
old-location: netvista\ndk_fn_close_object.htm
old-project: netvista
ms.assetid: 9547DCCE-6B3C-434F-A8CA-1AA59AB7152A
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDK_FN_CLOSE_OBJECT, NdkCloseObject, NdkCloseObject callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCloseObject, netvista.ndk_fn_close_object
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
-	NdkCloseObject
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_CLOSE_OBJECT callback


## -description


The <i>NdkCloseObject</i> (<i>NDK_FN_CLOSE_OBJECT</i>) function initiates a close request for an NDK  object.


## -parameters




### -param *pNdkObject [in]

A pointer to the object header (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>) for the object to close.


### -param CloseCompletion [in]

A pointer to an <i>NdkCloseCompletion</i> close completion callback function  (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439862">NDK_FN_CLOSE_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value for the NDK provider to pass back to the <i>NdkCloseCompletion</i> function that is specified in the <i>CloseCompletion</i> parameter.


## -returns



The 
     <i>NdkCloseObject</i> function returns one of the following NTSTATUS codes.

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
The NDK object is closed. The provider will not call the <i>NdkCloseCompletion</i>  function.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The  request  is pending,  the provider will call the <i>NdkCloseCompletion</i> function to complete the operation asynchronously. The close request has been successfully initiated, but it might not be completed. 

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



The function dispatch table for each  type of NDK object   includes  an <i>NDK_FN_CLOSE_OBJECT</i> function pointer. Close  requests are asynchronous. An  NDK consumer must not access the object after a close request is started. 

The NDK provider must ensure that the <i>NdkCloseCompletion</i> function (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439862">NDK_FN_CLOSE_COMPLETION</a>) is the last callback called for the object that is closing. The provider must ensure that all outstanding asynchronous requests are completed and all in-progress callbacks have returned and further callbacks are prevented before the provider calls the <i>NdkCloseCompletion</i> function.   After the provider calls the <i>NdkCloseCompletion</i> function, the provider not call any  completion functions or notification callback functions  for the object.




## -see-also




<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439853">NDK_CONNECTOR_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439855">NDK_CQ_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439862">NDK_FN_CLOSE_COMPLETION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>
 

 

