---
UID: NC:ndkpi.NDK_FN_CREATE_CQ
title: NDK_FN_CREATE_CQ
author: windows-driver-content
description: The NdkCreateCq (NDK_FN_CREATE_CQ) function creates an NDK completion queue (CQ) object.
old-location: netvista\ndk_fn_create_cq.htm
old-project: netvista
ms.assetid: 25F820D4-04AF-488E-BBDA-1E9D82B7483E
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_create_cq, NdkCreateCq callback function [Network Drivers Starting with Windows Vista], NdkCreateCq, NDK_FN_CREATE_CQ, NDK_FN_CREATE_CQ, ndkpi/NdkCreateCq
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
-	NdkCreateCq
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_CREATE_CQ callback


## -description


The <i>NdkCreateCq</i> (<i>NDK_FN_CREATE_CQ</i>) function creates an NDK completion queue (CQ) object.


## -prototype


````
NDK_FN_CREATE_CQ NdkCreateCq;

NTSTATUS NdkCreateCq(
  _In_     NDK_ADAPTER                     *pNdkAdapter,
  _In_     ULONG                           CqDepth,
  _In_     NDK_FN_CQ_NOTIFICATION_CALLBACK CqNotification,
  _In_opt_ PVOID                           CqNotificationContext,
  _In_opt_ GROUP_AFFINITY                  *Affinity,
  _In_     NDK_FN_CREATE_COMPLETION        CreateCompletion,
  _In_opt_ PVOID                           RequestContext,
           _Outptr_ NDK_CQ                 **ppNdkCq
)
{ ... }
````


## -parameters




### -param *pNdkAdapter [in]

A pointer to an NDK adapter object (<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>).


### -param CqDepth [in]

The maximum number of completion entries that the CQ can hold. This value must be less than or equal  to the <b>MaxCqDepth</b> value that is specified  in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure.


### -param CqNotification [in]

A pointer to the <i>NdkCqNotificationCallback</i> function   (<a href="..\ndkpi\nc-ndkpi-ndk_fn_cq_notification_callback.md">NDK_FN_CQ_NOTIFICATION_CALLBACK</a>) that the provider uses to notify the consumer when request completions are queued in the CQ. The provider will not call <i>NdkCqNotificationCallback</i> unless the consumer arms the notification with the <i>NdkArmCq</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_arm_cq.md">NDK_FN_ARM_CQ</a>) function.


### -param CqNotificationContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCqNotificationCallback</i> function that is specified in the <i>CqNotification</i> parameter.


### -param *Affinity [in, optional]

An affinity mask (<a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a>) that provides preferred processors that the consumer would choose to run the <i>NdkCqNotificationCallback</i> callbacks. Providers should honor the processor preferences if their underlying hardware allows it, but consumers cannot assume that <i>NdkCqNotificationCallback</i> callbacks will occur only on the preferred processors. Set <i>Affinity</i> to NULL if there are no preferred processors.


### -param CreateCompletion [in]

A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.


### -param RequestContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.


#### - **ppNdkCq

A pointer to a completion queue (CQ) object (<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>) is returned in this location if the request succeeds without returning STATUS_PENDING. If <i>NdkCreateCq</i> returns STATUS_PENDING this parameter is ignored and the created object is returned  with the callback that is specified in the  <i>CreateCompletion</i> parameter.


#### - ppNdkCq

A pointer to a completion queue (CQ) object (<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>) is returned in this location if the request succeeds without returning STATUS_PENDING. If <i>NdkCreateCq</i> returns STATUS_PENDING this parameter is ignored and the created object is returned  with the callback that is specified in the  <i>CreateCompletion</i> parameter.


## -returns


The 
     <i>NDK_FN_CREATE_CQ</i> function returns one of the following NTSTATUS codes.
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
The CQ object was created successfully and returned with the <i>*ppNdkCq</i> parameter.

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the  requested <i>CqDepth</i> value is greater than the <b>MaxCqDepth</b> value that is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The request  failed due to insufficient resources. 

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


The <i>NdkCreateCq</i> function creates an NDK completion queue (CQ) object. If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkCq</i> parameter. If <i>NdkCreateCq</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.



## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_cq_notification_callback.md">NDK_FN_CQ_NOTIFICATION_CALLBACK</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>

<a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a>

<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_arm_cq.md">NDK_FN_ARM_CQ</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_CQ callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

