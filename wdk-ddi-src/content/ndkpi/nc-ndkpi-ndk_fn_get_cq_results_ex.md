---
UID: NC:ndkpi.NDK_FN_GET_CQ_RESULTS_EX
title: NDK_FN_GET_CQ_RESULTS_EX
author: windows-driver-content
description: The NdkGetCqResultsEx (NDK_FN_GET_CQ_RESULTS_EX) function removes completions from an NDK completion queue (CQ) object.
old-location: netvista\ndk_fn_get_cq_results_ex.htm
old-project: netvista
ms.assetid: DC2782AB-BDFA-45C2-BC2E-ED4B946597D4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndk_fn_get_cq_results_ex, NDK_FN_GET_CQ_RESULTS_EX callback function [Network Drivers Starting with Windows Vista], NDK_FN_GET_CQ_RESULTS_EX, NDK_FN_GET_CQ_RESULTS_EX, NDK_FN_GET_CQ_RESULTS_EX, ndkpi/NDK_FN_GET_CQ_RESULTS_EX
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndkpi.h
apiname:
-	NDK_FN_GET_CQ_RESULTS_EX
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_GET_CQ_RESULTS_EX callback


## -description


The <i>NdkGetCqResultsEx</i> (<i>NDK_FN_GET_CQ_RESULTS_EX</i>) function removes completions from an NDK completion queue (CQ) object. This function is identical to the <i>NdkGetCqResults</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_cq_results.md">NDK_FN_GET_CQ_RESULTS</a>) function, except that it retrieves an array of <a href="..\ndkpi\ns-ndkpi-_ndk_result_ex.md">NDK_RESULT_EX</a> structures instead of an array of <a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a> structures.


## -prototype


````
NDK_FN_GET_CQ_RESULTS_EX NDK_FN_GET_CQ_RESULTS_EX;

ULONG NDK_FN_GET_CQ_RESULTS_EX(
  _In_ NDK_CQ                                          *pNdkCq,
       _Out_writes_to_(nResults, return) NDK_RESULT_EX Results[],
  _In_ ULONG                                           nResults
)
{ ... }
````


## -parameters




### -param *pNdkCq [in]

A pointer to an NDK completion queue (CQ) object  (<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>).


### -param Results[]


### -param nResults [in]

The size, in elements, of the <i>Results</i> array. That is, the maximum number of completions to remove from the CQ.


#### - Results

An array of <a href="..\ndkpi\ns-ndkpi-_ndk_result_ex.md">NDK_RESULT_EX</a> structures that will be filled with completion results that were removed from the CQ.


## -returns



The <i>NDK_FN_GET_CQ_RESULTS_EX</i> function returns the number of completions that were removed from the CQ. 

Zero means there were no completions in the CQ.




## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_result_ex.md">NDK_RESULT_EX</a>



<a href="https://msdn.microsoft.com/87150E2F-64F2-4EAB-A8B3-8E77622BE36C">NDKPI Completion Handling Requirements</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_cq_results.md">NDK_FN_GET_CQ_RESULTS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_CQ_RESULTS_EX callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

