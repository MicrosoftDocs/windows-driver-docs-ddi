---
UID: NC:ndkpi.NDK_FN_WRITE
title: NDK_FN_WRITE
author: windows-driver-content
description: The NdkWrite (NDK_FN_WRITE) function posts a write request on an NDK queue pair (QP).
old-location: netvista\ndk_fn_write.htm
old-project: netvista
ms.assetid: 4AE7E897-556B-40C4-BC12-31D957552690
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDK_FN_WRITE, NDK_FN_WRITE callback, NDK_OP_FLAG_DEFER, NDK_OP_FLAG_READ_FENCE, NDK_OP_FLAG_SILENT_SUCCESS, NdkWrite, NdkWrite callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkWrite, netvista.ndk_fn_write
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
-	NdkWrite
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_WRITE callback function


## -description


The <i>NdkWrite</i> (<i>NDK_FN_WRITE</i>) function posts a write request on an NDK queue pair (QP).


## -parameters




### -param *pNdkQp [in]

A pointer to an NDK queue pair (QP) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>).


### -param RequestContext [in, optional]

A context value to be returned in the <b>RequestContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a> structure for this request.



### -param NDK_SGE

An array of SGE structures (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439936">NDK_SGE</a>) that represent the buffers holding the data to write.

### -param nSge [in]

The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.


### -param RemoteAddress [in]

The remote address to write to, provided in the local host's byte order. The NDK consumer might have added an offset to the remotely-provided value.


### -param RemoteToken [in]

The remotely-provided memory token, an opaque array of bytes from the NDK consumer. 


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
Indicates the successful completion of this request but does not generate a completion event in the outbound completion queue. However, requests that fail do generate a completion in the completion queue.

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



The <i>NdkWrite</i> function returns one of the following NTSTATUS codes.

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
The request was posted successfully. A completion entry will be queued to the completion queue (CQ) when the work request is completed.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The queue pair (QP) is not connected.
 

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



<i>NdkWrite</i> posts a write request on a queue pair (QP).




## -see-also




<a href="https://msdn.microsoft.com/DA2D0FCA-D84B-4599-A560-8F87A0918D99">NDKPI Deferred Processing Scheme</a>



<a href="https://msdn.microsoft.com/2BF6F253-FCB4-4A61-9A67-81092F3C44E4">NDKPI Work Request Posting Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439936">NDK_SGE</a>
 

 

