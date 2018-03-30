---
UID: NC:ndkpi.NDK_FN_GET_CQ_RESULTS
title: NDK_FN_GET_CQ_RESULTS
author: windows-driver-content
description: The NdkGetCqResults (NDK_FN_GET_CQ_RESULTS) function removes completions from an NDK completion queue (CQ) object.
old-location: netvista\ndk_fn_get_cq_results.htm
old-project: netvista
ms.assetid: CDCDCF99-4A81-43FE-8A3D-0726699905BB
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_FN_GET_CQ_RESULTS, NdkGetCqResults, NdkGetCqResults callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetCqResults, netvista.ndk_fn_get_cq_results
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
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_GET_CQ_RESULTS callback


## -description


The <i>NdkGetCqResults</i> (<i>NDK_FN_GET_CQ_RESULTS</i>) function removes completions from an NDK completion queue (CQ) object.


## -parameters




### -param *pNdkCq [in]

A pointer to an NDK completion queue (CQ) object  (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a>).


### -param Results[]


### -param nResults [in]

The size, in elements, of the <i>Results</i> array. That is, the maximum number of completions to remove from the CQ.


#### - Results

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a> structures that will be filled with completion results that were removed from the CQ.


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
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_CQ_RESULTS callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
