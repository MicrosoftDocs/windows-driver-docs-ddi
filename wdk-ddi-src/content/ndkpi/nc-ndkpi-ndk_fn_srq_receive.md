---
UID: NC:ndkpi.NDK_FN_SRQ_RECEIVE
title: NDK_FN_SRQ_RECEIVE (ndkpi.h)
description: The NdkSrqReceive (NDK_FN_SRQ_RECEIVE) function posts a receive request on an NDK shared receive queue (SRQ).
old-location: netvista\ndk_fn_srq_receive.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_FN_SRQ_RECEIVE callback function"]
ms.keywords: NDK_FN_SRQ_RECEIVE, NDK_FN_SRQ_RECEIVE callback, NdkSrqReceive, NdkSrqReceive callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkSrqReceive, netvista.ndk_fn_srq_receive
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
 - NDK_FN_SRQ_RECEIVE
 - ndkpi/NDK_FN_SRQ_RECEIVE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NdkSrqReceive
---

# NDK_FN_SRQ_RECEIVE callback function


## -description

The <i>NdkSrqReceive</i> (<i>NDK_FN_SRQ_RECEIVE</i>) function posts a receive request on an NDK shared receive queue (SRQ).

## -parameters

### -param pNdkSrq 

[in]
A pointer to an NDK shared receive queue (SRQ) object
(<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq">NDK_SRQ</a>).

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
     <i>NdkSrqReceive</i> function returns one of the following NTSTATUS codes.

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
The receive request was posted successfully. A completion entry will be queued to the completion queue (CQ) when the request is completed.


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

<i>NdkSrqReceive</i> posts a receive request to a shared receive queue (SRQ).

## -see-also

<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_sge">NDK_SGE</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq">NDK_SRQ</a>
