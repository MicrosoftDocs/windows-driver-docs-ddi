---
UID: NC:ndkpi.NDK_FN_BIND
title: NDK_FN_BIND
description: The NdkBind (NDK_FN_BIND) function binds a memory window to a specific sub-region of a memory region (MR).
old-location: netvista\ndk_fn_bind.htm
tech.root: netvista
ms.assetid: F363C538-A5D7-4A08-B7CD-CA7D7346AC10
ms.date: 05/02/2018
ms.keywords: NDK_FN_BIND, NDK_FN_BIND callback, NDK_OP_FLAG_ALLOW_REMOTE_READ, NDK_OP_FLAG_ALLOW_REMOTE_WRITE, NDK_OP_FLAG_DEFER, NDK_OP_FLAG_READ_FENCE, NDK_OP_FLAG_SILENT_SUCCESS, NdkBind, NdkBind callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkBind, netvista.ndk_fn_bind
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
-	NdkBind
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_BIND callback function


## -description


The <i>NdkBind</i> (<i>NDK_FN_BIND</i>) function binds a memory window to a specific sub-region of a memory region (MR).


## -parameters




### -param *pNdkQp [in]

A pointer to an NDK queue pair (QP) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>).


### -param RequestContext [in, optional]

A context value to return in the <b>RequestContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a> structure for this request.


### -param *pMr [in]

A pointer to an NDK memory region (MR) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>).


### -param *pMw [in]

A pointer to an NDK memory window (MW) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439926">NDK_MW</a>).


### -param VirtualAddress [in]

A virtual address that must be greater than or equal to the virtual address of the MDL for the MR and less than the virtual address of the MDL for the MR plus the value in the <i>Length</i> parameter.

Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a> macro to obtain the virtual address of the MDL for the MR.


### -param Length [in]

The length of the MR to bind to the MW. 


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
Indicates the successful completion of this request does not generate a completion event in the outbound completion queue. However, requests that fail do generate a completion in the completion queue.

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
<td width="40%"><a id="NDK_OP_FLAG_ALLOW_REMOTE_READ"></a><a id="ndk_op_flag_allow_remote_read"></a><dl>
<dt><b>NDK_OP_FLAG_ALLOW_REMOTE_READ</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%">
Enable read access to the memory window for any connected peer. To access the memory window,  the connected peers must have a valid token.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_ALLOW_REMOTE_WRITE"></a><a id="ndk_op_flag_allow_remote_write"></a><dl>
<dt><b>NDK_OP_FLAG_ALLOW_REMOTE_WRITE</b></dt>
<dt>0x00000030</dt>
</dl>
</td>
<td width="60%">
Enable write access to the memory window for any connected peer. To access the memory window,  the connected peers must have a valid token.

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
     <i>NdkBind</i> function returns one of the following NTSTATUS codes.

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
The queue pair (QP) is not connected.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
The memory region does not allow the type of access requested for the memory window. The NDK_OP_FLAG_ALLOW_WRITE  flag requires a memory region that was registered with the NDK_MR_FLAG_ALLOW_LOCAL_WRITE flag.

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



<i>NdkBind</i> binds a memory window (MW) to a specific sub-region of a memory region (MR).

The address in the <i>VirtualAddress</i> parameter must be an address within the virtually contiguous region that is described by the MDL chain that was specified during memory registration. The address must be treated by the provider as an index into the memory region. The address must not be used by the provider as a valid virtual address for reading or writing buffer contents.

After this call returns, the remote token will be available with the <i>NdkGetRemotetokenFromMw</i> function (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439898">NDK_FN_GET_REMOTE_TOKEN_FROM_MW</a>).

This function does not support a zero-based virtual address.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>



<a href="https://msdn.microsoft.com/DA2D0FCA-D84B-4599-A560-8F87A0918D99">NDKPI Deferred Processing Scheme</a>



<a href="https://msdn.microsoft.com/2BF6F253-FCB4-4A61-9A67-81092F3C44E4">NDKPI Work Request Posting Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439898">NDK_FN_GET_REMOTE_TOKEN_FROM_MW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439926">NDK_MW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a>
 

 

