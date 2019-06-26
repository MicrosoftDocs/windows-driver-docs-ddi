---
UID: NC:ndkpi.NDK_FN_GET_CQ_RESULTS
title: NDK_FN_GET_CQ_RESULTS (ndkpi.h)
description: The NdkGetCqResults (NDK_FN_GET_CQ_RESULTS) function removes completions from an NDK completion queue (CQ) object.
old-location: netvista\ndk_fn_get_cq_results.htm
tech.root: netvista
ms.assetid: CDCDCF99-4A81-43FE-8A3D-0726699905BB
ms.date: 05/02/2018
ms.keywords: NDK_FN_GET_CQ_RESULTS, NDK_FN_GET_CQ_RESULTS callback, NdkGetCqResults, NdkGetCqResults callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetCqResults, netvista.ndk_fn_get_cq_results
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndkpi.h
api_name:
- NdkGetCqResults
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

A pointer to an NDK completion queue (CQ) object  (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>).


### -param Results[]

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a> structures that will be filled with completion results that were removed from the CQ.

### -param nResults [in]

The size, in elements, of the <i>Results</i> array. That is, the maximum number of completions to remove from the CQ.

## -returns



The <i>NDK_FN_GET_CQ_RESULTS</i> function returns the number of completions that were removed from the CQ. 

Zero means there were no completions in the CQ.




## -remarks



<i>NdkGetCqResults</i> removes completions from a completion queue (CQ).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-completion-handling-requirements">NDKPI Completion Handling Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_cq_dispatch">NDK_CQ_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a>
 

 

