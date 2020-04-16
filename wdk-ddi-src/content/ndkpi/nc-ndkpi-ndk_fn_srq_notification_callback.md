---
UID: NC:ndkpi.NDK_FN_SRQ_NOTIFICATION_CALLBACK
title: NDK_FN_SRQ_NOTIFICATION_CALLBACK (ndkpi.h)
description: The NdkSrqNotificationCallback (NDK_FN_SRQ_NOTIFICATION_CALLBACK) function provides NDK shared receive queue (SRQ) notifications from an NDK provider.
old-location: netvista\ndk_fn_srq_notification_callback.htm
tech.root: netvista
ms.assetid: 3063F991-DDC5-4E52-979B-6CFCD11A604C
ms.date: 05/02/2018
keywords: ["NDK_FN_SRQ_NOTIFICATION_CALLBACK callback function"]
ms.keywords: NDK_FN_SRQ_NOTIFICATION_CALLBACK, NDK_FN_SRQ_NOTIFICATION_CALLBACK callback, NdkSrqNotificationCallback, NdkSrqNotificationCallback callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkSrqNotificationCallback, netvista.ndk_fn_srq_notification_callback
f1_keywords:
 - "ndkpi/NdkSrqNotificationCallback"
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
- NdkSrqNotificationCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_SRQ_NOTIFICATION_CALLBACK callback function


## -description


The <i>NdkSrqNotificationCallback</i> (<i>NDK_FN_SRQ_NOTIFICATION_CALLBACK</i>) function provides NDK shared receive queue (SRQ) notifications from an NDK provider.


## -parameters




### -param SrqNotificationContext [in, optional]

A context area that was specified in the <i>SrqNotificationContext</i> parameter of the <i>NdkCreateSrq</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_srq">NDK_FN_CREATE_SRQ</a>) function when the SRQ  object was created.


### -param SrqStatus [in]

Indicates if a fatal SRQ error occurred. The following status codes are defined:




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
The SRQ is operating normally.


</td>
</tr>
<tr>
<td width="40%">
<a id="STATUS_INTERNAL_ERROR"></a><a id="status_internal_error"></a>STATUS_INTERNAL_ERROR

</td>
<td width="60%">
A catastrophic error occurred on the SRQ. The SRQ is unusable. All of the associated queue pairs (QPs) are also unusable. No future completions will be reported. This error usually indicates a hardware error.

</td>
</tr>
</table>
 


## -remarks



<div class="alert"><b>Note</b>  This routine is implemented by the NDK consumer and passed to the NDK provider.</div>
<div> </div>
An NDK provider calls the <i>NdkSrqNotificationCallback</i> function when the number of receive requests that are queued on the SRQ falls below the minimum number of queued receive requests (<i>NotifyThreshold</i>). The   <i>NotifyThreshold</i> is an input parameter to the <i>NdkCreateSrq</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_srq">NDK_FN_CREATE_SRQ</a>)  and <i>NdkModifySrq</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_modify_srq">NDK_FN_MODIFY_SRQ</a>)  functions.



