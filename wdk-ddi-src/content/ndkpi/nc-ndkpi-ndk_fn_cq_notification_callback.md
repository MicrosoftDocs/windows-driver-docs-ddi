---
UID: NC:ndkpi.NDK_FN_CQ_NOTIFICATION_CALLBACK
title: NDK_FN_CQ_NOTIFICATION_CALLBACK (ndkpi.h)
description: The NdkCqNotificationCallback (NDK_FN_CQ_NOTIFICATION_CALLBACK) function is called by the NDK provider to notify the consumer about a completion queue (CQ) event.
old-location: netvista\ndk_fn_cq_notification_callback.htm
tech.root: netvista
ms.assetid: 88035020-9585-41EC-9C63-29DDED779C39
ms.date: 05/02/2018
ms.keywords: NDK_FN_CQ_NOTIFICATION_CALLBACK, NDK_FN_CQ_NOTIFICATION_CALLBACK callback, NdkCqNotificationCallback, NdkCqNotificationCallback callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCqNotificationCallback, netvista.ndk_fn_cq_notification_callback
f1_keywords:
 - "ndkpi/NdkCqNotificationCallback"
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
- NdkCqNotificationCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_CQ_NOTIFICATION_CALLBACK callback function


## -description


The <i>NdkCqNotificationCallback</i> (<i>NDK_FN_CQ_NOTIFICATION_CALLBACK</i>) function is called by the NDK provider to notify the consumer about  a completion queue (CQ) event.


## -parameters




### -param CqNotificationContext [in, optional]

A context area that was specified in the <i>CqNotificationContext</i> parameter of the <i>NdkCreateCq</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_cq">NDK_FN_CREATE_CQ</a>) function when the completion queue (CQ)  object was created.


### -param CqStatus [in]

Indicates the CQ error status. The following status codes are defined:



<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="STATUS_SUCCESS"></a><a id="status_success"></a>STATUS_SUCCESS

</td>
<td width="60%">
Indicates the CQ is operating normally.

</td>
</tr>
<tr>
<td width="40%">
<a id="STATUS_BUFFER_OVERFLOW"></a><a id="status_buffer_overflow"></a>STATUS_BUFFER_OVERFLOW

</td>
<td width="60%">
Indicates more completions than that maximum that the CQ can hold were attempted to be queued on the CQ and the CQ is  unusable. All of the associated queue pairs (QPs) are also unusable. No future completions will be reported. A STATUS_BUFFER_OVERFLOW error usually indicates a programming error.

</td>
</tr>
<tr>
<td width="40%">
<a id="STATUS_INTERNAL_ERROR"></a><a id="status_internal_error"></a>STATUS_INTERNAL_ERROR

</td>
<td width="60%">
Indicates a  fatal error occurred on the CQ and the CQ is  unusable. All of the associated queue pairs (QPs) are also unusable.  No future completions will be reported. A STATUS_INTERNAL_ERROR error usually indicates a hardware error.

</td>
</tr>
</table>
 


## -remarks



An NDK provider calls <i>NdkCqNotificationCallback</i> to notify the consumer about  a completion queue (CQ) event.

The NDK consumer specified the <i>NdkCqNotificationCallback</i> function  in the <i>CqNotificationContext</i> parameter of the <i>NdkCreateCq</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_cq">NDK_FN_CREATE_CQ</a>) function when the completion queue (CQ) object was created.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-completion-handling-requirements">NDKPI Completion Handling Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_cq">NDK_FN_CREATE_CQ</a>
 

 

