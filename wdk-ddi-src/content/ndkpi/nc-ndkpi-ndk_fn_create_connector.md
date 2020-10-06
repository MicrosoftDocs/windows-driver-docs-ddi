---
UID: NC:ndkpi.NDK_FN_CREATE_CONNECTOR
title: NDK_FN_CREATE_CONNECTOR (ndkpi.h)
description: The NdkCreateConnector (NDK_FN_CREATE_CONNECTOR) function creates an NDK connector object.
old-location: netvista\ndk_fn_create_connector.htm
tech.root: netvista
ms.assetid: E800AC7B-EAEB-44FB-96ED-890C6442F066
ms.date: 05/02/2018
keywords: ["NDK_FN_CREATE_CONNECTOR callback function"]
ms.keywords: NDK_FN_CREATE_CONNECTOR, NDK_FN_CREATE_CONNECTOR callback, NdkCreateConnector, NdkCreateConnector callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCreateConnector, netvista.ndk_fn_create_connector
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
 - NDK_FN_CREATE_CONNECTOR
 - ndkpi/NDK_FN_CREATE_CONNECTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NdkCreateConnector
---

# NDK_FN_CREATE_CONNECTOR callback function


## -description

The <i>NdkCreateConnector</i> (<i>NDK_FN_CREATE_CONNECTOR</i>) function creates an NDK connector object.

## -parameters

### -param pNdkAdapter 

[in]
A pointer to an NDK adapter object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter">NDK_ADAPTER</a>).

### -param CreateCompletion 

[in]
A pointer to an <i>NdkCreateCompletion</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.

### -param RequestContext 

[in, optional]
A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.

### -param *ppNdkConnector

A pointer to an NDK connector object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>) is returned in this location if the request succeeds without returning STATUS_PENDING. If <i>NdkCreateConnector</i> returns STATUS_PENDING  this parameter is ignored and the created object is returned with the callback that is specified in the  <i>CreateCompletion</i> parameter.

## -returns

The 
     <i>NdkCreateConnector</i> function returns one of the following NTSTATUS codes.

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
The connector was created successfully and returned with the <i>*ppNdkConnector</i> parameter.

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

The <i>NdkCreateConnector</i> function creates an NDK connector object. If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkConnector</i> parameter. If <i>NdkCreateConnector</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter">NDK_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter_dispatch">NDK_ADAPTER_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>