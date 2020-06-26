---
UID: NC:ndkpi.NDK_FN_GET_REMOTE_TOKEN_FROM_MR
title: NDK_FN_GET_REMOTE_TOKEN_FROM_MR (ndkpi.h)
description: The NdkGetRemoteTokenFromMr (NDK_FN_GET_REMOTE_TOKEN_FROM_MR) function gets a memory token from a remote NDK memory region (MR).
old-location: netvista\ndk_fn_get_remote_token_from_mr.htm
tech.root: netvista
ms.assetid: 272DB944-E772-4E98-8918-AE0CEE440E3E
ms.date: 05/02/2018
keywords: ["NDK_FN_GET_REMOTE_TOKEN_FROM_MR callback function"]
ms.keywords: NDK_FN_GET_REMOTE_TOKEN_FROM_MR, NDK_FN_GET_REMOTE_TOKEN_FROM_MR callback, NdkGetRemoteTokenFromMr, NdkGetRemoteTokenFromMr callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetRemoteTokenFromMr, netvista.ndk_fn_get_remote_token_from_mr
f1_keywords:
 - "ndkpi/NdkGetRemoteTokenFromMr"
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
- NdkGetRemoteTokenFromMr
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_GET_REMOTE_TOKEN_FROM_MR callback function


## -description


The <i>NdkGetRemoteTokenFromMr</i> (<i>NDK_FN_GET_REMOTE_TOKEN_FROM_MR</i>) function gets a memory token from a remote NDK memory region (MR).


## -parameters




### -param pNdkMr [in]

A pointer to an NDK memory region (MR) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>).


## -returns



The 
     <i>NdkGetRemoteTokenFromMr</i> function returns a local memory region token.




## -remarks



<i>NdkGetRemoteTokenFromMr</i> can be called after an <i>NdkRegisterMr</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_register_mr">NDK_FN_REGISTER_MR</a>) or <i>NdkInitializeFastRegisterMr</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_initialize_fast_register_mr">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>)  call is completed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_initialize_fast_register_mr">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_register_mr">NDK_FN_REGISTER_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>
 

 

