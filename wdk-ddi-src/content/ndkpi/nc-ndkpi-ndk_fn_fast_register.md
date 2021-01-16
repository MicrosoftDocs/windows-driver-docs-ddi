---
UID: NC:ndkpi.NDK_FN_FAST_REGISTER
title: NDK_FN_FAST_REGISTER (ndkpi.h)
description: The NdkFastRegister (NDK_FN_FAST_REGISTER) function fast-registers an array of adapter logical pages over an existing memory region.
old-location: netvista\ndk_fn_fast_register.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_FN_FAST_REGISTER callback function"]
ms.keywords: NDK_FN_FAST_REGISTER, NDK_FN_FAST_REGISTER callback, NDK_OP_FLAG_ALLOW_LOCAL_WRITE, NDK_OP_FLAG_ALLOW_REMOTE_READ, NDK_OP_FLAG_ALLOW_REMOTE_WRITE, NDK_OP_FLAG_DEFER, NDK_OP_FLAG_READ_FENCE, NDK_OP_FLAG_SILENT_SUCCESS, NdkFastRegister, NdkFastRegister callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkFastRegister, netvista.ndk_fn_fast_register
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
 - NDK_FN_FAST_REGISTER
 - ndkpi/NDK_FN_FAST_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NDK_FN_FAST_REGISTER
---

# NDK_FN_FAST_REGISTER callback function


## -description

The <i>NdkFastRegister</i> (<i>NDK_FN_FAST_REGISTER</i>) function fast-registers an array of adapter logical pages over an existing memory region.

## -parameters

### -param pNdkQp 

[in]
A pointer to an NDK queue pair (QP) object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>).

### -param RequestContext 

[in, optional]
A  context value to return in the <b>RequestContext</b> member of the <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a> structure for this request.

### -param pMr 

[in]
A pointer to an NDK memory region (MR) object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>) that was initialized for fast registration.

### -param AdapterPageCount 

[in]
The number of pages in the <i>AdapterPageArray</i> parameter. The size of each page in the <i>AdapterPageArray</i> is <b>PAGE_SIZE</b> bytes.

### -param NDK_LOGICAL_ADDRESS

### -param FBO 

[in]
The first byte offset (FBO) within the first page. The registered region starts at this offset.

### -param Length 

[in]
The length, in bytes, of the region being registered starting at the FBO. The length must be less than or equal to the total number of bytes that are represented by the first set (<i>AdapterPageCount</i>) of pages that are contained in the <i>AdapterPageArray</i> array minus the FBO.

### -param BaseVirtualAddress 

[in]
The consumer-specified virtual address value to refer to the first byte location of the memory region. This value must be a multiple of <b>PAGE_SIZE</b> plus FBO. So, the allowed values include  FBO, or FBO plus  n times the <b>PAGE_SIZE</b> where n is greater than or equal to zero. Zero is a valid value only if FBO is zero.

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
<td width="40%"><a id="NDK_OP_FLAG_ALLOW_REMOTE_READ"></a><a id="ndk_op_flag_allow_remote_read"></a><dl>
<dt><b>NDK_OP_FLAG_ALLOW_REMOTE_READ</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%">
Enable read access to the memory region for any connected peer. To access the memory region,  the connected peers must have a valid token.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_ALLOW_LOCAL_WRITE"></a><a id="ndk_op_flag_allow_local_write"></a><dl>
<dt><b>NDK_OP_FLAG_ALLOW_LOCAL_WRITE</b></dt>
<dt>0x00000010</dt>
</dl>
</td>
<td width="60%">
Allow local write access to the memory region.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_ALLOW_REMOTE_WRITE"></a><a id="ndk_op_flag_allow_remote_write"></a><dl>
<dt><b>NDK_OP_FLAG_ALLOW_REMOTE_WRITE</b></dt>
<dt>0x00000030</dt>
</dl>
</td>
<td width="60%">
Enable write access to the memory region for any connected peer. To access the memory region,  the connected peers must have a valid token.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_DEFER"></a><a id="ndk_op_flag_defer"></a><dl>
<dt><b>NDK_OP_FLAG_DEFER</b></dt>
<dt>0x00000200</dt>
</dl>
</td>
<td width="60%">
Indicates to the NDK provider that it may defer indicating the request to hardware for processing. For more information about this flag, see <a href="/windows-hardware/drivers/network/ndkpi-deferred-processing-scheme">NDKPI Deferred Processing Scheme</a>.

<b>Note</b>  This flag is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.

</td>
</tr>
</table>
 


#### - AdapterPageArray

An array of adapter logical addresses (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_logical_address_mapping">NDK_LOGICAL_ADDRESS</a>) where each address is the starting logical address for a page. Each address must be aligned  pages that are <b>PAGE_SIZE</b> bytes in length. Consecutive addresses in the array are not necessarily consecutive in terms of the logical address space, but the array as a whole represents a virtually contiguous memory region from the perspective of the host system.

## -returns

The 
     <i>NDK_FN_FAST_REGISTER</i> function returns one of the following NTSTATUS codes.

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
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
The memory region was not initialized for remote access during fast-register initialization but the fast-register work request specified <b>NDK_OP_FLAG_ALLOW_REMOTE_READ</b> or <b>NDK_OP_FLAG_ALLOW_REMOTE_WRITE</b>.

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

<i>NdkFastRegister</i> fast-registers an array of adapter logical pages over an existing memory region that is  initialized for fast registration.

After  this call returns, the memory region token for remote access is available with the <i>NdkGetRemoteTokenFromMr</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_remote_token_from_mr">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a>)  function of the MR.

<i>NdkFastRegister</i> does not support zero-based virtual addresses.

If the <b>NDK_ADAPTER_FLAG_RDMA_READ_SINK_NOT_REQUIRED</b> flag is not set in the <b>AdapterFlags</b> member of the <a href="/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a> structure, an NDK consumer must pass the <b>NDK_OP_FLAG_RDMA_READ_SINK</b> flag when it registers memory that might be used as the sink buffer for an RDMA read request. Certain NDK providers might require the enabling of special access rights on the sink buffer for an RDMA read request. This flag allows such providers to support registration requests appropriately. Note that buffers might be registered for multiple purposes, therefore this flag might be accompanied by others. 

If an NDK consumer passes the <b>NDK_OP_FLAG_RDMA_READ_SINK</b> flag on an adapter for which the <b>NDK_ADAPTER_FLAG_RDMA_READ_SINK_NOT_REQUIRED</b> flag is set in the <b>AdapterFlags</b> member of the  <a href="/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a> structure, the provider is not required to handle the <b>NDK_OP_FLAG_RDMA_READ_SINK</b> flag and must not fail the request  due to the presence of this flag.

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-deferred-processing-scheme">NDKPI Deferred Processing Scheme</a>



<a href="/windows-hardware/drivers/network/ndkpi-work-request-posting-requirements">NDKPI Work Request Posting Requirements</a>



<a href="/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_remote_token_from_mr">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_logical_address_mapping">NDK_LOGICAL_ADDRESS</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a>

