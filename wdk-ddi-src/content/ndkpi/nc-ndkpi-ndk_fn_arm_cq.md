---
UID: NC:ndkpi.NDK_FN_ARM_CQ
title: NDK_FN_ARM_CQ (ndkpi.h)
description: The NdkArmCq (NDK_FN_ARM_CQ) function arms an NDK completion queue (CQ) notification.
old-location: netvista\ndk_fn_arm_cq.htm
tech.root: netvista
ms.assetid: 8204EC7B-8F90-4F34-BFFB-9F1574AF69BC
ms.date: 05/02/2018
ms.keywords: NDK_FN_ARM_CQ, NDK_FN_ARM_CQ callback, NdkArmCq, NdkArmCq callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkArmCq, netvista.ndk_fn_arm_cq
f1_keywords:
 - "ndkpi/NdkArmCq"
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
- NdkArmCq
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_ARM_CQ callback function


## -description


The <i>NdkArmCq</i> (<i>NDK_FN_ARM_CQ</i>) function arms an NDK completion queue (CQ) notification. 


## -parameters




### -param *pNdkCq [in]

A pointer to an NDK completion queue object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>).



### -param Type [in]

The type of notification to arm. The following notification types are defined:



<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="NDK_CQ_NOTIFY_ERRORS"></a><a id="ndk_cq_notify_errors"></a>NDK_CQ_NOTIFY_ERRORS

</td>
<td width="60%">
Notify if there are any completion queue errors such as a completion queue overrun or catastrophic failure.

</td>
</tr>
<tr>
<td width="40%">
<a id="NDK_CQ_NOTIFY_ANY"></a><a id="ndk_cq_notify_any"></a>NDK_CQ_NOTIFY_ANY

</td>
<td width="60%">
Notify of the next successful completion in the completion queue.

</td>
</tr>
<tr>
<td width="40%">
<a id="NDK_CQ_NOTIFY_SOLICITED"></a><a id="ndk_cq_notify_solicited"></a>NDK_CQ_NOTIFY_SOLICITED

</td>
<td width="60%">
Notify when the completion queue receives a send request that includes the ND_OP_FLAG_SEND_AND_SOLICIT_EVENT flag.

</td>
</tr>
</table>
 


## -remarks



After the NDK consumer arms a completion queue (CQ) notification, the provider calls the <i>NdkCqNotificationCallback</i> callback function (the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_cq_notification_callback">NDK_FN_CQ_NOTIFICATION_CALLBACK</a> routine that the consumer  specified when the CQ was created with the <i>NdkCreateCq</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_cq">NDK_FN_CREATE_CQ</a>) function) when the specified type of notification is due.

If the CQ is closed while a call to <i>NdkCqNotificationCallback</i> is in-progress, the close request will remain pending until <i>NdkCqNotificationCallback</i> returns control  to the provider. After the close request is completed, the provider will not call  <i>NdkCqNotificationCallback</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-completion-handling-requirements">NDKPI Completion Handling Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq_dispatch">NDK_CQ_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_cq_notification_callback">NDK_FN_CQ_NOTIFICATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_cq">NDK_FN_CREATE_CQ</a>
 

 

