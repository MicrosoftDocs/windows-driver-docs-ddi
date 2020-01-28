---
UID: NC:ndkpi.NDK_FN_DEREGISTER_MR
title: NDK_FN_DEREGISTER_MR (ndkpi.h)
description: The NdkDeregisterMr (NDK_FN_DEREGISTER_MR) function deregisters a memory region that was previously registered with the NdkRegisterMr (NDK_FN_REGISTER_MR) function.
old-location: netvista\ndk_fn_deregister_mr.htm
tech.root: netvista
ms.assetid: 6446F3A6-550D-4498-87CF-B6FE50C67BBE
ms.date: 05/02/2018
ms.keywords: NDK_FN_DEREGISTER_MR, NDK_FN_DEREGISTER_MR callback, NdkDeregisterMr, NdkDeregisterMr callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkDeregisterMr, netvista.ndk_fn_deregister_mr
f1_keywords:
 - "ndkpi/NdkDeregisterMr"
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
- NdkDeregisterMr
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_DEREGISTER_MR callback function


## -description


The <i>NdkDeregisterMr</i> (<i>NDK_FN_DEREGISTER_MR</i>) function deregisters a memory region that was previously registered with the <i>NdkRegisterMr</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_register_mr">NDK_FN_REGISTER_MR</a>) function.


## -parameters




### -param *pNdkMr [in]

A pointer to an NDK memory region (MR) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>) that is in the registered state.


### -param RequestCompletion [in]

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


## -returns



The <i>NdkDeregisterMr</i> function returns one of the following NTSTATUS codes.

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
Deregistration was completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 

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
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_register_mr">NDK_FN_REGISTER_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>
 

 

