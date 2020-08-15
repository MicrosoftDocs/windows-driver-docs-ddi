---
UID: NC:ndkpi.NDK_FN_GET_REMOTE_TOKEN_FROM_MW
title: NDK_FN_GET_REMOTE_TOKEN_FROM_MW (ndkpi.h)
description: The NdkGetRemoteTokenFromMw (NDK_FN_GET_REMOTE_TOKEN_FROM_MW) function gets a memory token from a remote NDK memory window (MW).
old-location: netvista\ndk_fn_get_remote_token_from_mw.htm
tech.root: netvista
ms.assetid: 893B53DA-B858-4E21-9DD9-D244702ACF46
ms.date: 05/02/2018
keywords: ["NDK_FN_GET_REMOTE_TOKEN_FROM_MW callback function"]
ms.keywords: NDK_FN_GET_REMOTE_TOKEN_FROM_MW, NDK_FN_GET_REMOTE_TOKEN_FROM_MW callback, NdkGetRemoteTokenFromMw, NdkGetRemoteTokenFromMw callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetRemoteTokenFromMw, netvista.ndk_fn_get_remote_token_from_mw
f1_keywords:
 - "ndkpi/NdkGetRemoteTokenFromMw"
 - "NdkGetRemoteTokenFromMw"
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
- NdkGetRemoteTokenFromMw
targetos: Windows
req.typenames: 
---

# NDK_FN_GET_REMOTE_TOKEN_FROM_MW callback function


## -description


The <i>NdkGetRemoteTokenFromMw</i> (<i>NDK_FN_GET_REMOTE_TOKEN_FROM_MW</i>) function gets a memory token from a remote NDK memory window (MW).


## -parameters




### -param pNdkMw 
[in]
A pointer to an NDK memory window (MW) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mw">NDK_MW</a>).


## -returns



The 
     <i>NdkGetRemoteTokenFromMw</i> function returns a remote memory region token.




## -remarks



 After an <i>NdkBind</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_bind">NDK_FN_BIND</a>) call returns control to the caller, <i>NdkGetRemoteTokenFromMw</i> can be called to retrieve the remote token.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_bind">NDK_FN_BIND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mw">NDK_MW</a>
 

 

