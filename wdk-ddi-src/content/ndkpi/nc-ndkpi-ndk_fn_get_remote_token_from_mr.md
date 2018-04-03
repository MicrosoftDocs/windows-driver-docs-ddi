---
UID: NC:ndkpi.NDK_FN_GET_REMOTE_TOKEN_FROM_MR
title: NDK_FN_GET_REMOTE_TOKEN_FROM_MR
author: windows-driver-content
description: The NdkGetRemoteTokenFromMr (NDK_FN_GET_REMOTE_TOKEN_FROM_MR) function gets a memory token from a remote NDK memory region (MR).
old-location: netvista\ndk_fn_get_remote_token_from_mr.htm
old-project: netvista
ms.assetid: 272DB944-E772-4E98-8918-AE0CEE440E3E
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDK_FN_GET_REMOTE_TOKEN_FROM_MR, NdkGetRemoteTokenFromMr, NdkGetRemoteTokenFromMr callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetRemoteTokenFromMr, netvista.ndk_fn_get_remote_token_from_mr
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
-	NdkGetRemoteTokenFromMr
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_GET_REMOTE_TOKEN_FROM_MR callback


## -description


The <i>NdkGetRemoteTokenFromMr</i> (<i>NDK_FN_GET_REMOTE_TOKEN_FROM_MR</i>) function gets a memory token from a remote NDK memory region (MR).


## -parameters




### -param *pNdkMr [in]

A pointer to an NDK memory region (MR) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>).


## -returns



The 
     <i>NdkGetRemoteTokenFromMr</i> function returns a local memory region token.




## -remarks



<i>NdkGetRemoteTokenFromMr</i> can be called after an <i>NdkRegisterMr</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439908">NDK_FN_REGISTER_MR</a>) or <i>NdkInitializeFastRegisterMr</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439900">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>)  call is completed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439900">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439908">NDK_FN_REGISTER_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>
 

 

