---
UID: NC:ndkpi.NDK_FN_GET_CQ_RESULTS_EX
title: NDK_FN_GET_CQ_RESULTS_EX (ndkpi.h)
description: The NdkGetCqResultsEx (NDK_FN_GET_CQ_RESULTS_EX) function removes completions from an NDK completion queue (CQ) object.
old-location: netvista\ndk_fn_get_cq_results_ex.htm
tech.root: netvista
ms.assetid: DC2782AB-BDFA-45C2-BC2E-ED4B946597D4
ms.date: 05/02/2018
keywords: ["NDK_FN_GET_CQ_RESULTS_EX callback function"]
ms.keywords: NDK_FN_GET_CQ_RESULTS_EX, NDK_FN_GET_CQ_RESULTS_EX callback, NDK_FN_GET_CQ_RESULTS_EX callback function [Network Drivers Starting with Windows Vista], ndkpi/NDK_FN_GET_CQ_RESULTS_EX, netvista.ndk_fn_get_cq_results_ex
f1_keywords:
 - "ndkpi/NDK_FN_GET_CQ_RESULTS_EX"
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.40 and later.
req.target-min-winversvr: Windows Server 2012 R2
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
- NDK_FN_GET_CQ_RESULTS_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_GET_CQ_RESULTS_EX callback function


## -description


The <i>NdkGetCqResultsEx</i> (<i>NDK_FN_GET_CQ_RESULTS_EX</i>) function removes completions from an NDK completion queue (CQ) object. This function is identical to the <i>NdkGetCqResults</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_cq_results">NDK_FN_GET_CQ_RESULTS</a>) function, except that it retrieves an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result_ex">NDK_RESULT_EX</a> structures instead of an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a> structures.


## -parameters




### -param *pNdkCq [in]

A pointer to an NDK completion queue (CQ) object  (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>).


### -param Results[]

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result_ex">NDK_RESULT_EX</a> structures that will be filled with completion results that were removed from the CQ.

### -param nResults [in]

The size, in elements, of the <i>Results</i> array. That is, the maximum number of completions to remove from the CQ.


## -returns



The <i>NDK_FN_GET_CQ_RESULTS_EX</i> function returns the number of completions that were removed from the CQ. 

Zero means there were no completions in the CQ.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-completion-handling-requirements">NDKPI Completion Handling Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_cq_results">NDK_FN_GET_CQ_RESULTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result_ex">NDK_RESULT_EX</a>
 

 

