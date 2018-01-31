---
UID: NC:ndkpi.NDK_FN_CREATE_MR
title: NDK_FN_CREATE_MR
author: windows-driver-content
description: The NdkCreateMr (NDK_FN_CREATE_MR) function creates an NDK memory region (MR) object.
old-location: netvista\ndk_fn_create_mr.htm
old-project: netvista
ms.assetid: AD0F1FA1-0CE5-40BE-86B8-537C9C8C0B8F
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_create_mr, NdkCreateMr callback function [Network Drivers Starting with Windows Vista], NdkCreateMr, NDK_FN_CREATE_MR, NDK_FN_CREATE_MR, ndkpi/NdkCreateMr
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
-	NdkCreateMr
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_CREATE_MR callback


## -description


The <i>NdkCreateMr</i> (<i>NDK_FN_CREATE_MR</i>) function creates an NDK memory region (MR) object.


## -prototype


````
NDK_FN_CREATE_MR NdkCreateMr;

NTSTATUS NdkCreateMr(
  _In_     NDK_PD                   *pNdkPd,
  _In_     BOOLEAN                  FastRegister,
  _In_     NDK_FN_CREATE_COMPLETION CreateCompletion,
  _In_opt_ PVOID                    RequestContext,
           _Outptr_ NDK_MR          **ppNdkMr
)
{ ... }
````


## -parameters




#### - *pNdkPd [in]

A pointer to an NDK protection domain (PD) object (<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>).


#### - FastRegister [in]

If TRUE, MR is for fast-register only. Otherwise, MR is for normal register only.


#### - CreateCompletion [in]

A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.


#### - RequestContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.


#### - **ppNdkMr

A pointer to the created MR object (<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>) is returned in this location if request succeeds without returning <b>STATUS_PENDING</b>. If <i>NdkCreateMr</i> returns <b>STATUS_PENDING</b>, this parameter is ignored and the created object is returned  with the callback that is specified in the  <i>CreateCompletion</i> parameter.


#### - pNdkPd [in]

A pointer to an NDK protection domain (PD) object (<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>).


#### - ppNdkMr

A pointer to the created MR object (<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>) is returned in this location if request succeeds without returning <b>STATUS_PENDING</b>. If <i>NdkCreateMr</i> returns <b>STATUS_PENDING</b>, this parameter is ignored and the created object is returned  with the callback that is specified in the  <i>CreateCompletion</i> parameter.


## -returns


The 
     <i>NdkCreateMr</i> function returns one of the following NTSTATUS codes.
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
The MR object was created successfully and returned with the <i>*ppNdkMr</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter(<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 

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
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table> 



## -remarks


The <i>NdkCreateMr</i> function creates an NDK memory region (MR) object that can be used for memory registration and fast registration requests. If the function returns <b>STATUS_SUCCESS</b>, the created object is returned in the <i>ppNdkMr</i> parameter. If <i>NdkCreateMr</i> returns <b>STATUS_PENDING</b>, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.



## -see-also

<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_MR callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

