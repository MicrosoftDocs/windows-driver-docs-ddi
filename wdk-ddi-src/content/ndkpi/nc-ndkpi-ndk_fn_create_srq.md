---
UID: NC:ndkpi.NDK_FN_CREATE_SRQ
title: NDK_FN_CREATE_SRQ (ndkpi.h)
description: The NdkCreateSrq (NDK_FN_CREATE_SRQ) function creates an NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_fn_create_srq.htm
tech.root: netvista
ms.assetid: 83125C65-021F-4EEE-8819-B73752908DE7
ms.date: 05/02/2018
ms.keywords: NDK_FN_CREATE_SRQ, NDK_FN_CREATE_SRQ callback, NdkCreateSrq, NdkCreateSrq callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCreateSrq, netvista.ndk_fn_create_srq
ms.topic: callback
f1_keywords:
 - "ndkpi/NdkCreateSrq"
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
- NdkCreateSrq
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_CREATE_SRQ callback function


## -description


The <i>NdkCreateSrq</i> (<i>NDK_FN_CREATE_SRQ</i>) function creates an NDK shared receive queue (SRQ) object.


## -parameters




### -param *pNdkPd [in]

A pointer to an NDK protection domain (PD) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>).


### -param SrqDepth [in]

The maximum number of receive requests that can be outstanding over the SRQ. This value  must be less than or equal to the value in the <b>MaxSrqDepth</b> member that is specified in the <a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-_ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.


### -param MaxReceiveRequestSge [in]

The maximum number of SGEs that are supported in a single receive request. This value must be less than or equal to the value in the <b>MaxReceiveRequestSge</b> member that is specified in the NDK_ADAPTER_INFO structure.


### -param NotifyThreshold [in]

The minimum number of queued receive requests for triggering SRQ notification callbacks.


### -param SrqNotification [in, optional]

An optional <i>NdkSrqNotificationCallback</i> function(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_srq_notification_callback">NDK_FN_SRQ_NOTIFICATION_CALLBACK</a>) which the provider calls if the  queued receive request count falls below the threshold that is specified in the  <i>NotifyThreshold</i> parameter.


### -param SrqNotificationContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkSrqNotificationCallback</i> function that is specified in the <i>SrqNotification</i> parameter.


### -param *Affinity [in, optional]

An affinity mask (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a>) that specifies preferred processors that the consumer would choose to run the <i>NdkSrqNotificationCallback</i> callbacks. Providers should honor the processor preferences if their underlying hardware allows it, but consumers cannot assume that <i>NdkSrqNotificationCallback</i> callbacks will occur only on the preferred processors. Set <i>Affinity</i> to NULL if there are no preferred processors.


### -param CreateCompletion [in]

A pointer to an <i>NdkCreateCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.


### -param RequestContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.


#### -param **ppNdkSrq

A pointer to a created SRQ object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq">NDK_SRQ</a>) is returned in this location if the request succeeds without returning STATUS_PENDING. If the request returns STATUS_PENDING then this parameter is ignored and the created object is returned with the callback that is specified in the  <i>CreateCompletion</i> parameter.

## -returns



The 
     <i>NdkCreateSrq</i> function returns one of the following NTSTATUS codes.

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
The SRQ object was created successfully and returned with the  <i>*ppNdkSrq</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the requested <i>SrqDepth</i> or <i>MaxReceiveRequestSge</i> is not within the limits that are specified in the <a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-_ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.

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



The <i>NdkCreateSrq</i> function creates an NDK shared receive queue (SRQ) object. If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkSrq</i> parameter. If <i>NdkCreateSrq</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-_ndk_adapter_info">NDK_ADAPTER_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_srq_notification_callback">NDK_FN_SRQ_NOTIFICATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq">NDK_SRQ</a>
 

 

