---
UID: NC:ndkpi.NDK_FN_RECEIVE
title: NDK_FN_RECEIVE (ndkpi.h)
description: The NdkReceive (NDK_FN_RECEIVE) function posts a receive request on an NDK queue pair (QP).
old-location: netvista\ndk_fn_receive.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_FN_RECEIVE callback function"]
ms.keywords: NDK_FN_RECEIVE, NDK_FN_RECEIVE callback, NdkReceive, NdkReceive callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkReceive, netvista.ndk_fn_receive
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
 - NDK_FN_RECEIVE
 - ndkpi/NDK_FN_RECEIVE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NDK_FN_RECEIVE
---

# NDK_FN_RECEIVE callback function


## -description

   The <i>NdkReceive</i> (<i>NDK_FN_RECEIVE</i>) function posts a receive request on an NDK queue pair (QP).

## -parameters

### -param pNdkQp 

[in]
A pointer to an NDK queue pair (QP) object
(<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>).

### -param RequestContext 

[in, optional]
A context value to be returned in the <b>RequestContext</b> member of the <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a> structure for this request.

### -param NDK_SGE

An array of SGE structures (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_sge">NDK_SGE</a>) that represent the buffers to receive incoming data.

### -param nSge 

[in]
The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.

## -returns

The 
     <i>NdkReceive</i> function returns one of the following NTSTATUS codes.

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
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>

## -remarks

<i>NdkReceive</i> posts a receive request on a queue pair (QP).

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-work-request-posting-requirements">NDKPI Work Request Posting Requirements</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_sge">NDK_SGE</a>

