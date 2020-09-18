---
UID: NC:ndkpi.NDK_FN_READ
title: NDK_FN_READ (ndkpi.h)
description: The NdkRead (NDK_FN_READ) function posts a read request on an NDK queue pair (QP).
old-location: netvista\ndk_fn_read.htm
tech.root: netvista
ms.assetid: A6D2C017-0D50-4AD7-9241-110C97F5FE92
ms.date: 05/02/2018
keywords: ["NDK_FN_READ callback function"]
ms.keywords: NDK_FN_READ, NDK_FN_READ callback, NDK_OP_FLAG_DEFER, NDK_OP_FLAG_RDMA_READ_LOCAL_INVALIDATE, NDK_OP_FLAG_READ_FENCE, NDK_OP_FLAG_SILENT_SUCCESS, NdkRead, NdkRead callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkRead, netvista.ndk_fn_read
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NDK_FN_READ
 - ndkpi/NDK_FN_READ
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NdkRead
---

# NDK_FN_READ callback function


## -description

The <i>NdkRead</i> (<i>NDK_FN_READ</i>) function posts a read request on an NDK queue pair (QP).

## -parameters

### -param pNdkQp 

[in]
A pointer to an NDK queue pair (QP) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>).

### -param RequestContext 

[in, optional]
A context value to be returned in the <b>RequestContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a> structure for this request.

### -param NDK_SGE

An array of SGE structures (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_sge">NDK_SGE</a>) that represent the buffers to place incoming data into.

### -param nSge 

[in]
The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.

### -param RemoteAddress 

[in]
A remote address to read from that is presented in the local host's byte order. The NDK consumer can   add  an offset  to the remotely-provided value.

### -param RemoteToken 

[in]
A remotely-provided memory token that  is an opaque array of bytes from the NDK consumer.

### -param Flags 

[in]
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
<td width="40%"><a id="NDK_OP_FLAG_RDMA_READ_LOCAL_INVALIDATE"></a><a id="ndk_op_flag_rdma_read_local_invalidate"></a><dl>
<dt><b>NDK_OP_FLAG_RDMA_READ_LOCAL_INVALIDATE</b></dt>
<dt>0x00000200</dt>
</dl>
</td>
<td width="60%">
If this flag is set and the provider also reports <b>NDK_ADAPTER_FLAG_RDMA_READ_LOCAL_INVALIDATE_SUPPORTED</b> adapter capability in the <a href="https://docs.microsoft.com/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a> structure, successful completion of the <i>NdkRead</i> function means that the first buffer specified in the <i>pSgl</i> parameter is invalidated. Unsuccessful completion leaves the buffer and token in an undefined state. This flag is ignored if the provider does not report <b>NDK_ADAPTER_FLAG_RDMA_READ_LOCAL_INVALIDATE_SUPPORTED</b> adapter capability in the <b>NDK_ADAPTER_INFO</b> structure.

<b>Note</b>  This flag is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_DEFER"></a><a id="ndk_op_flag_defer"></a><dl>
<dt><b>NDK_OP_FLAG_DEFER</b></dt>
<dt>0x00000200</dt>
</dl>
</td>
<td width="60%">
Indicates to the NDK provider that it may defer indicating the request to hardware for processing. For more information about this flag, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-deferred-processing-scheme">NDKPI Deferred Processing Scheme</a>.

<b>Note</b>  This flag is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.

</td>
</tr>
</table>

## -returns

The 
     <i>NdkRead</i> function returns one of the following NTSTATUS codes.

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
<dt><b>STATUS_REMOTE_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
	The request tried to read beyond the size of the remote memory.


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

<i>NdkRead</i> posts a read request on a queue pair (QP).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-deferred-processing-scheme">NDKPI Deferred Processing Scheme</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-work-request-posting-requirements">NDKPI Work Request Posting Requirements</a>



<a href="https://docs.microsoft.com/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_arm_cq">NDK_FN_ARM_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_sge">NDK_SGE</a>

