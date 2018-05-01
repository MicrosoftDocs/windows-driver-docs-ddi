---
UID: NC:ndkpi.NDK_FN_SRQ_RECEIVE
title: NDK_FN_SRQ_RECEIVE
author: windows-driver-content
description: The NdkSrqReceive (NDK_FN_SRQ_RECEIVE) function posts a receive request on an NDK shared receive queue (SRQ).
old-location: netvista\ndk_fn_srq_receive.htm
old-project: netvista
ms.assetid: 1D615DEA-5599-4A3D-AEE7-BDBFE9D40C47
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDK_FN_SRQ_RECEIVE, NDK_FN_SRQ_RECEIVE callback, NdkSrqReceive, NdkSrqReceive callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkSrqReceive, netvista.ndk_fn_srq_receive
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
-	NdkSrqReceive
product: Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_SRQ_RECEIVE callback function


## -description


The <i>NdkSrqReceive</i> (<i>NDK_FN_SRQ_RECEIVE</i>) function posts a receive request on an NDK shared receive queue (SRQ).


## -parameters




### -param *pNdkSrq [in]

A pointer to an NDK shared receive queue (SRQ) object
(<a href="https://msdn.microsoft.com/library/windows/hardware/hh439939">NDK_SRQ</a>).


### -param RequestContext [in, optional]

A context value to be returned in the <b>RequestContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a> structure for this request.



### -param NDK_SGE


### -param nSge [in]

The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.


#### - pSgl

An array of SGE structures (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439936">NDK_SGE</a>) that represent the buffers to receive incoming data.



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




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439936">NDK_SGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439939">NDK_SRQ</a>
 

 

