---
UID: NC:ndkpi.NDK_FN_GET_CQ_RESULTS_EX
title: NDK_FN_GET_CQ_RESULTS_EX
author: windows-driver-content
description: The NdkGetCqResultsEx (NDK_FN_GET_CQ_RESULTS_EX) function removes completions from an NDK completion queue (CQ) object.
old-location: netvista\ndk_fn_get_cq_results_ex.htm
old-project: netvista
ms.assetid: DC2782AB-BDFA-45C2-BC2E-ED4B946597D4
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDK_FN_GET_CQ_RESULTS_EX, NDK_FN_GET_CQ_RESULTS_EX callback, NDK_FN_GET_CQ_RESULTS_EX callback function [Network Drivers Starting with Windows Vista], ndkpi/NDK_FN_GET_CQ_RESULTS_EX, netvista.ndk_fn_get_cq_results_ex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndkpi.h
api_name:
-	NDK_FN_GET_CQ_RESULTS_EX
product: Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_GET_CQ_RESULTS_EX callback function


## -description


The <i>NdkGetCqResultsEx</i> (<i>NDK_FN_GET_CQ_RESULTS_EX</i>) function removes completions from an NDK completion queue (CQ) object. This function is identical to the <i>NdkGetCqResults</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439891">NDK_FN_GET_CQ_RESULTS</a>) function, except that it retrieves an array of <a href="https://msdn.microsoft.com/library/windows/hardware/dn265509">NDK_RESULT_EX</a> structures instead of an array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a> structures.


## -parameters




### -param *pNdkCq [in]

A pointer to an NDK completion queue (CQ) object  (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a>).


### -param Results[]


### -param nResults [in]

The size, in elements, of the <i>Results</i> array. That is, the maximum number of completions to remove from the CQ.


#### - Results

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/dn265509">NDK_RESULT_EX</a> structures that will be filled with completion results that were removed from the CQ.


## -returns



The <i>NDK_FN_GET_CQ_RESULTS_EX</i> function returns the number of completions that were removed from the CQ. 

Zero means there were no completions in the CQ.




## -see-also




<a href="https://msdn.microsoft.com/87150E2F-64F2-4EAB-A8B3-8E77622BE36C">NDKPI Completion Handling Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439891">NDK_FN_GET_CQ_RESULTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265509">NDK_RESULT_EX</a>
 

 

