---
UID: NC:ndkpi.NDK_FN_GET_CQ_RESULTS
title: NDK_FN_GET_CQ_RESULTS
author: windows-driver-content
description: The NdkGetCqResults (NDK_FN_GET_CQ_RESULTS) function removes completions from an NDK completion queue (CQ) object.
old-location: netvista\ndk_fn_get_cq_results.htm
old-project: netvista
ms.assetid: CDCDCF99-4A81-43FE-8A3D-0726699905BB
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDK_FN_GET_CQ_RESULTS, NDK_FN_GET_CQ_RESULTS callback, NdkGetCqResults, NdkGetCqResults callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetCqResults, netvista.ndk_fn_get_cq_results
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
-	NdkGetCqResults
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_GET_CQ_RESULTS callback function


## -description


The <i>NdkGetCqResults</i> (<i>NDK_FN_GET_CQ_RESULTS</i>) function removes completions from an NDK completion queue (CQ) object.


## -parameters




### -param *pNdkCq [in]

A pointer to an NDK completion queue (CQ) object  (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a>).


### -param Results[]

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a> structures that will be filled with completion results that were removed from the CQ.

### -param nResults [in]

The size, in elements, of the <i>Results</i> array. That is, the maximum number of completions to remove from the CQ.

## -returns



The <i>NDK_FN_GET_CQ_RESULTS</i> function returns the number of completions that were removed from the CQ. 

Zero means there were no completions in the CQ.




## -remarks



<i>NdkGetCqResults</i> removes completions from a completion queue (CQ).




## -see-also




<a href="https://msdn.microsoft.com/87150E2F-64F2-4EAB-A8B3-8E77622BE36C">NDKPI Completion Handling Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439855">NDK_CQ_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a>
 

 

