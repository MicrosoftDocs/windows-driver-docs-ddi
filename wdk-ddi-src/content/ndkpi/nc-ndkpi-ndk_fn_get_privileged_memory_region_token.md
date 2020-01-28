---
UID: NC:ndkpi.NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN
title: NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN (ndkpi.h)
description: The NdkGetPrivilegedMemoryRegionToken (NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN) function gets an NDK privileged memory region token.
old-location: netvista\ndk_fn_get_privileged_memory_region_token.htm
tech.root: netvista
ms.assetid: A6295FEE-3633-42E7-A2EA-BA0D3C9E4101
ms.date: 05/02/2018
ms.keywords: NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN, NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN callback, NdkGetPrivilegedMemoryRegionToken, NdkGetPrivilegedMemoryRegionToken callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetPrivilegedMemoryRegionToken, netvista.ndk_fn_get_privileged_memory_region_token
f1_keywords:
 - "ndkpi/NdkGetPrivilegedMemoryRegionToken"
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
- NdkGetPrivilegedMemoryRegionToken
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN callback function


## -description


The <i>NdkGetPrivilegedMemoryRegionToken</i> (<i>NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN</i>) function gets an NDK privileged  memory region token.


## -parameters




### -param *pNdkPd [in]

A pointer to an NDK protection domain (PD) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>).


### -param *pToken [out]

A memory token value is returned in this location.


## -remarks



<i>NdkGetPrivilegedMemoryRegionToken</i> gets a privileged  memory region token value that allows adapter logical addresses  to be used directly without memory registration. This token must provide LOCAL_READ and LOCAL_WRITE access. A provider must never allow remote access for the privileged memory region token.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>
 

 

