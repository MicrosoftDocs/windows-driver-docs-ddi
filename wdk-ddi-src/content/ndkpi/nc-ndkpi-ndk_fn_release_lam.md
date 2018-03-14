---
UID: NC:ndkpi.NDK_FN_RELEASE_LAM
title: NDK_FN_RELEASE_LAM
author: windows-driver-content
description: The NdkReleaseLam (NDK_FN_RELEASE_LAM) function releases an NDK adapter logical address mapping (LAM).
old-location: netvista\ndk_fn_release_lam.htm
old-project: netvista
ms.assetid: 8CEBDCCE-5B71-443D-9DE5-F789E16843D7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_FN_RELEASE_LAM, NdkReleaseLam, NdkReleaseLam callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkReleaseLam, netvista.ndk_fn_release_lam
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
-	NdkReleaseLam
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_RELEASE_LAM callback


## -description


The <i>NdkReleaseLam</i> (<i>NDK_FN_RELEASE_LAM</i>) function releases an NDK adapter logical address mapping (LAM).


## -prototype


````
NDK_FN_RELEASE_LAM NdkReleaseLam;

VOID NdkReleaseLam(
  _In_ NDK_ADAPTER                 *pNdkAdapter,
  _In_ NDK_LOGICAL_ADDRESS_MAPPING *pNdkLAM
)
{ ... }
````


## -parameters




### -param *pNdkAdapter [in]

A pointer to an NDK adapter object
(<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>).


### -param *pNdkLAM [in]

A pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_logical_address_mapping.md">NDK_LOGICAL_ADDRESS_MAPPING</a> structure that was previously initialized by calling the <i>NdkBuildLAM</i>  (<a href="..\ndkpi\nc-ndkpi-ndk_fn_build_lam.md">NDK_FN_BUILD_LAM</a>) function.



## -returns



None




## -remarks



<i>NdkReleaseLam</i> releases an adapter logical address mapping (LAM). The associated MDL  remains unchanged. That is, the MDL is in the same state it hand when it was  passed to the <i>NdkBuildLam</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_build_lam.md">NDK_FN_BUILD_LAM</a>) function. The NDK consumer must not release a LAM until after all of the work requests that use the LAM are completed.




## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_build_lam.md">NDK_FN_BUILD_LAM</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_logical_address_mapping.md">NDK_LOGICAL_ADDRESS_MAPPING</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>



 

 


