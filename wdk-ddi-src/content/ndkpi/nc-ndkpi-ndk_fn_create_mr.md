---
UID: NC:ndkpi.NDK_FN_CREATE_MR
title: NDK_FN_CREATE_MR (ndkpi.h)
description: The NdkCreateMr (NDK_FN_CREATE_MR) function creates an NDK memory region (MR) object.
old-location: netvista\ndk_fn_create_mr.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_FN_CREATE_MR callback function"]
ms.keywords: NDK_FN_CREATE_MR, NDK_FN_CREATE_MR callback, NdkCreateMr, NdkCreateMr callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCreateMr, netvista.ndk_fn_create_mr
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NDK_FN_CREATE_MR
 - ndkpi/NDK_FN_CREATE_MR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NdkCreateMr
---

# NDK_FN_CREATE_MR callback function


## -description

The <i>NdkCreateMr</i> (<i>NDK_FN_CREATE_MR</i>) function creates an NDK memory region (MR) object.

## -parameters

### -param pNdkPd 

[in]
A pointer to an NDK protection domain (PD) object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>).

### -param FastRegister 

[in]
If TRUE, MR is for fast-register only. Otherwise, MR is for normal register only.

### -param CreateCompletion 

[in]
A pointer to an <i>NdkCreateCompletion</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.

### -param RequestContext 

[in, optional]
A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.

### -param *ppNdkMr

A pointer to the created MR object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>) is returned in this location if request succeeds without returning <b>STATUS_PENDING</b>. If <i>NdkCreateMr</i> returns <b>STATUS_PENDING</b>, this parameter is ignored and the created object is returned  with the callback that is specified in the  <i>CreateCompletion</i> parameter.

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
 The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter(<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 

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

The <i>NdkCreateMr</i> function creates an NDK memory region (MR) object that can be used for memory registration and fast registration requests. If the function returns <b>STATUS_SUCCESS</b>, the created object is returned in the <i>ppNdkMr</i> parameter. If <i>NdkCreateMr</i> returns <b>STATUS_PENDING</b>, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>
