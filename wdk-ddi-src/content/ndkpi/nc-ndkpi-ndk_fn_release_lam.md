---
UID: NC:ndkpi.NDK_FN_RELEASE_LAM
title: NDK_FN_RELEASE_LAM (ndkpi.h)
description: The NdkReleaseLam (NDK_FN_RELEASE_LAM) function releases an NDK adapter logical address mapping (LAM).
old-location: netvista\ndk_fn_release_lam.htm
tech.root: netvista
ms.assetid: 8CEBDCCE-5B71-443D-9DE5-F789E16843D7
ms.date: 05/02/2018
ms.keywords: NDK_FN_RELEASE_LAM, NDK_FN_RELEASE_LAM callback, NdkReleaseLam, NdkReleaseLam callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkReleaseLam, netvista.ndk_fn_release_lam
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
- NdkReleaseLam
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_RELEASE_LAM callback function


## -description


The <i>NdkReleaseLam</i> (<i>NDK_FN_RELEASE_LAM</i>) function releases an NDK adapter logical address mapping (LAM).


## -parameters




### -param *pNdkAdapter [in]

A pointer to an NDK adapter object
(<a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a>).


### -param *pNdkLAM [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439920">NDK_LOGICAL_ADDRESS_MAPPING</a> structure that was previously initialized by calling the <i>NdkBuildLAM</i>  (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439860">NDK_FN_BUILD_LAM</a>) function.



## -returns



None




## -remarks



<i>NdkReleaseLam</i> releases an adapter logical address mapping (LAM). The associated MDL  remains unchanged. That is, the MDL is in the same state it hand when it was  passed to the <i>NdkBuildLam</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439860">NDK_FN_BUILD_LAM</a>) function. The NDK consumer must not release a LAM until after all of the work requests that use the LAM are completed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439850">NDK_ADAPTER_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439860">NDK_FN_BUILD_LAM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439920">NDK_LOGICAL_ADDRESS_MAPPING</a>
 

 

