---
UID: NC:ndkpi.NDK_FN_CREATE_QP
title: NDK_FN_CREATE_QP (ndkpi.h)
description: The NdkCreateQp (NDK_FN_CREATE_QP) function creates an NDK queue pair (QP) object.
old-location: netvista\ndk_fn_create_qp.htm
tech.root: netvista
ms.assetid: 8B601E53-9BE9-4D84-819E-3B0BD07560BC
ms.date: 05/02/2018
keywords: ["NDK_FN_CREATE_QP callback function"]
ms.keywords: NDK_FN_CREATE_QP, NDK_FN_CREATE_QP callback, NdkCreateQp, NdkCreateQp callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCreateQp, netvista.ndk_fn_create_qp
f1_keywords:
 - "ndkpi/NdkCreateQp"
 - "NdkCreateQp"
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
- NdkCreateQp
targetos: Windows
req.typenames: 
---

# NDK_FN_CREATE_QP callback function


## -description


The <i>NdkCreateQp</i> (<i>NDK_FN_CREATE_QP</i>) function creates an NDK queue pair (QP) object.


## -parameters




### -param pNdkPd 
[in]
A pointer to an NDK protection domain (PD) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>).


### -param pReceiveCq 
[in]
A pointer to a completion queue (CQ) to use for receive request completions (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>).


### -param pInitiatorCq 
[in]
A pointer to a CQ to use for initiator request completions.


### -param QPContext 
[in, optional]
A context value to be returned in the <b>QPContext</b> member of the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a> structure for all requests that are posted over this QP.


### -param ReceiveQueueDepth 
[in]
The maximum number of receive requests that can be outstanding over the QP. This value must be less than or equal to the value in the  <b>MaxReceiveQueueDepth</b> member of the  <a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-_ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.


### -param InitiatorQueueDepth 
[in]
The maximum number of initiator requests that can be outstanding over the QP. This value must be less than or equal to the value in the  <b>MaxInitiatorQueueDepth</b> member of the  NDK_ADAPTER_INFO structure.


### -param MaxReceiveRequestSge 
[in]
The maximum number of SGEs that can be supported in a single receive request. This value must be less than or equal to the value in the  <b>MaxReceiveRequestSge</b> member of the  NDK_ADAPTER_INFO structure.


### -param MaxInitiatorRequestSge 
[in]
The maximum number of SGEs that can be supported in a single initiator request. This value must be less than or equal to the value in the  <b>MaxInitiatorRequestSge</b> member of the  NDK_ADAPTER_INFO structure.


### -param InlineDataSize 
[in]
The maximum amount of inline data in bytes that can be sent in a single send or write request. This value must be less than or equal to the value in the  <b>MaxInlineDataSize</b> member of the  NDK_ADAPTER_INFO structure.


### -param CreateCompletion 
[in]
A pointer to an <i>NdkCreateCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.


### -param RequestContext 
[in, optional]
A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.


#### -param *ppNdkQp

A pointer to a created QP object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>) is returned in this location if the request succeeds without returning STATUS_PENDING. If the request returns STATUS_PENDING then this parameter is ignored and the created object is returned with the callback that is specified in the  <i>CreateCompletion</i> parameter.


## -returns



The 
     <i>NdkCreateQp</i> function returns one of the following NTSTATUS codes.

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
The QP object was created successfully and returned with the <i>*ppNdkQp</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the requested <i>ReceiveQueueDepth</i>, <i>InitiatorQueueDepth</i>,  <i>MaxReceiveRequestSge</i>, <i>MaxInitiatorRequestSge</i>, or <i>InlineDataSize</i> are not within the limits that are specified in the  <a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-_ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.

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



The <i>NdkCreateQp</i> function creates an   NDK queue pair (QP) object.  A QP consists of a receive queue and an initiator queue. The receive queue is used to  post receive requests. An initiator queue is used for initiating send, bind, fast-register, read, write, and invalidate requests.

If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkQp</i> parameter. If <i>NdkCreateQp</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-_ndk_adapter_info">NDK_ADAPTER_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a>
 

 

