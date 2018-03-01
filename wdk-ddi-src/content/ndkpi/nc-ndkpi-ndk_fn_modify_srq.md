---
UID: NC:ndkpi.NDK_FN_MODIFY_SRQ
title: NDK_FN_MODIFY_SRQ
author: windows-driver-content
description: The NdkModifySrq (NDK_FN_MODIFY_SRQ) function modifies the size and notification threshold of an NDK shared receive queue (SRQ).
old-location: netvista\ndk_fn_modify_srq.htm
old-project: netvista
ms.assetid: ABB42AC6-8483-420C-B9A9-063C91E4FB13
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDK_FN_MODIFY_SRQ, NdkModifySrq, NdkModifySrq callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkModifySrq, netvista.ndk_fn_modify_srq
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
-	NdkModifySrq
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_MODIFY_SRQ callback


## -description


The <i>NdkModifySrq</i> (<i>NDK_FN_MODIFY_SRQ</i>) function modifies the size and notification threshold of an NDK  shared receive queue (SRQ).


## -prototype


````
NDK_FN_MODIFY_SRQ NdkModifySrq;

NTSTATUS NdkModifySrq(
  _In_     NDK_SRQ                   *pNdkSrq,
  _In_     ULONG                     SrqDepth,
  _In_     ULONG                     NotifyThreshold,
  _In_     NDK_FN_REQUEST_COMPLETION RequestCompletion,
  _In_opt_ PVOID                     RequestContext
)
{ ... }
````


## -parameters




### -param *pNdkSrq [in]

A pointer to an NDK shared receive queue (SRQ) object (<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>).


### -param SrqDepth [in]


The new size of the SRQ. The new size must be less than or equal to the  size that is specified in the <b>MaxSrqDepth</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure.
A size of zero means no depth modification is requested. That is,  the existing SRQ depth value must be preserved.


### -param NotifyThreshold [in]

The number of queued receive requests  that will trigger an SRQ notification callback. If this value is greater than zero,  the NDK provider must arm the SRQ notification to trigger  when the number of queued receive requests falls below the specified  value. If the number of queued receive requests is already below the threshold value at the time of this function call, an SRQ notification must be generated. After an SRQ notification is generated, further notifications are disarmed until the NDK consumer invokes this function again with a non-zero threshold value. If a threshold value of zero is specified, the provider must preserve the current SRQ notification threshold and arming status.


### -param RequestCompletion [in]

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


## -returns



The 
     <i>NdkModifySrq</i> function returns one of the following NTSTATUS codes.

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
The request was completed successfully.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the  value in the  <i>SrqDepth</i> parameter  is not within the limits that are specified in the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure.

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



<i>NdkModifySrq</i> modifies  the size and notification threshold for an NDK shared receive queue (SRQ) object (<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>). 




## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_MODIFY_SRQ callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

