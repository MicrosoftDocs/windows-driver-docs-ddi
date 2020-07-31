---
UID: NC:ndkpi.NDK_FN_GET_LOCAL_TOKEN_FROM_MR
title: NDK_FN_GET_LOCAL_TOKEN_FROM_MR (ndkpi.h)
description: The NdkGetLocalTokenFromMr (NDK_FN_GET_LOCAL_TOKEN_FROM_MR) function gets a memory token from a local NDK memory region (MR).
old-location: netvista\ndk_fn_get_local_token_from_mr.htm
tech.root: netvista
ms.assetid: 5578112B-1BB2-4130-BBCE-20025A0A609C
ms.date: 05/02/2018
keywords: ["NDK_FN_GET_LOCAL_TOKEN_FROM_MR callback function"]
ms.keywords: NDK_FN_GET_LOCAL_TOKEN_FROM_MR, NDK_FN_GET_LOCAL_TOKEN_FROM_MR callback, NdkGetLocalTokenFromMr, NdkGetLocalTokenFromMr callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetLocalTokenFromMr, netvista.ndk_fn_get_local_token_from_mr
f1_keywords:
 - "ndkpi/NdkGetLocalTokenFromMr"
 - "NdkGetLocalTokenFromMr"
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
- NdkGetLocalTokenFromMr
targetos: Windows
req.typenames: 
---

# NDK_FN_GET_LOCAL_TOKEN_FROM_MR callback function


## -description


The <i>NdkGetLocalTokenFromMr</i> (<i>NDK_FN_GET_LOCAL_TOKEN_FROM_MR</i>) function gets a memory token from a local NDK memory region (MR).


## -parameters




### -param pNdkMr [in]

A pointer to an NDK memory region (MR) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>).


## -returns



The 
     <i>NdkGetLocalTokenFromMr</i> function returns a local memory region token.




## -remarks



<i>NdkGetLocalTokenFromMr</i> returns a local memory region token.  <i>NdkGetLocalTokenFromMr</i> can be called after a call to  the  <i>NdkRegisterMr</i>  (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_register_mr">NDK_FN_REGISTER_MR</a>) function  or  <i>NdkInitializeFastRegisterMr</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_initialize_fast_register_mr">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>) function completes without errors.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_initialize_fast_register_mr">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_register_mr">NDK_FN_REGISTER_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>
 

 

