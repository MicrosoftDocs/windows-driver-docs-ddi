---
UID: NC:ndkpi.NDK_FN_INVALIDATE
title: NDK_FN_INVALIDATE
author: windows-driver-content
description: The NdkInvalidate (NDK_FN_INVALIDATE) function Invalidates a fast-register NDK memory region (MR) or memory window (MW).
old-location: netvista\ndk_fn_invalidate.htm
tech.root: netvista
ms.assetid: 79A39FEE-173F-4106-9759-97CF6BE5DA65
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NDK_FN_INVALIDATE, NDK_FN_INVALIDATE callback, NDK_OP_FLAG_DEFER, NDK_OP_FLAG_READ_FENCE, NDK_OP_FLAG_SILENT_SUCCESS, NdkInvalidate, NdkInvalidate callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkInvalidate, netvista.ndk_fn_invalidate
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
-	NdkInvalidate
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_INVALIDATE callback function


## -description


The <i>NdkInvalidate</i> (<i>NDK_FN_INVALIDATE</i>) function Invalidates a fast-register NDK memory region (MR) or memory window (MW).


## -parameters




### -param *pNdkQp [in]

A pointer to an NDK queue pair (QP) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>).


### -param RequestContext [in, optional]

A context value to return in the <b>RequestContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a> structure for this request.


### -param *pNdkMrOrMw [in]

A pointer to either an memory region (MR) object  (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>) or an memory (MW) object  (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439926">NDK_MW</a>) that is specified in an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a> structure. If an MR object is specified, the MR object must have been registered with the <i>NdkFastRegister</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439887">NDK_FN_FAST_REGISTER</a>) function.  The NDK  consumer must never specify an  MR object that was registered with the  <i>NdkRegister</i> (<a href="https://msdn.microsoft.com/082BBDE1-1B80-4306-96A1-DCD23910B0F7">NDK_FN_REGISTER</a>) function in the <i>pNdkMrOrMw</i>  parameter. Access to MR objects registered with the  <i>NdkRegister</i> (<i>NDK_FN_REGISTER</i>)) function can be removed with the NdkDeregisterMr (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439884">NDK_FN_DEREGISTER_MR</a>) function.


### -param Flags [in]

A bitwise OR of flags which specifies the operations that are allowed. The following flags are supported:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_SILENT_SUCCESS"></a><a id="ndk_op_flag_silent_success"></a><dl>
<dt><b>NDK_OP_FLAG_SILENT_SUCCESS</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Indicates the successful completion of this request does not generate a completion event in the outbound completion queue. However, requests that fail do generate an event in the completion queue.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_READ_FENCE"></a><a id="ndk_op_flag_read_fence"></a><dl>
<dt><b>NDK_OP_FLAG_READ_FENCE</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Indicates that all prior read requests must be complete before the hardware begins processing this request.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_DEFER"></a><a id="ndk_op_flag_defer"></a><dl>
<dt><b>NDK_OP_FLAG_DEFER</b></dt>
<dt>0x00000200</dt>
</dl>
</td>
<td width="60%">
Indicates to the NDK provider that it may defer indicating the request to hardware for processing. For more information about this flag, see <a href="https://msdn.microsoft.com/DA2D0FCA-D84B-4599-A560-8F87A0918D99">NDKPI Deferred Processing Scheme</a>.

<b>Note</b>  This flag is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.

</td>
</tr>
</table>
 


## -returns



The  
     <i>NdkInvalidate</i> function returns one of the following NTSTATUS codes.

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
The request was posted successfully. A completion entry will be queued to the CQ when the work request is completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The QP is not connected. 

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



<i>NdkInvalidate</i> invalidates an NDK fast-register MR or MW.




## -see-also




<a href="https://msdn.microsoft.com/87150E2F-64F2-4EAB-A8B3-8E77622BE36C">NDKPI Completion Handling Requirements</a>



<a href="https://msdn.microsoft.com/DA2D0FCA-D84B-4599-A560-8F87A0918D99">NDKPI Deferred Processing Scheme</a>



<a href="https://msdn.microsoft.com/2BF6F253-FCB4-4A61-9A67-81092F3C44E4">NDKPI Work Request Posting Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439884">NDK_FN_DEREGISTER_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439887">NDK_FN_FAST_REGISTER</a>



<a href="https://msdn.microsoft.com/082BBDE1-1B80-4306-96A1-DCD23910B0F7">NDK_FN_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439926">NDK_MW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a>
 

 

