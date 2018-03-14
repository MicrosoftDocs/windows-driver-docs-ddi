---
UID: NC:ndkpi.NDK_FN_GET_REMOTE_TOKEN_FROM_MW
title: NDK_FN_GET_REMOTE_TOKEN_FROM_MW
author: windows-driver-content
description: The NdkGetRemoteTokenFromMw (NDK_FN_GET_REMOTE_TOKEN_FROM_MW) function gets a memory token from a remote NDK memory window (MW).
old-location: netvista\ndk_fn_get_remote_token_from_mw.htm
old-project: netvista
ms.assetid: 893B53DA-B858-4E21-9DD9-D244702ACF46
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_FN_GET_REMOTE_TOKEN_FROM_MW, NdkGetRemoteTokenFromMw, NdkGetRemoteTokenFromMw callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetRemoteTokenFromMw, netvista.ndk_fn_get_remote_token_from_mw
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
-	NdkGetRemoteTokenFromMw
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_GET_REMOTE_TOKEN_FROM_MW callback


## -description


The <i>NdkGetRemoteTokenFromMw</i> (<i>NDK_FN_GET_REMOTE_TOKEN_FROM_MW</i>) function gets a memory token from a remote NDK memory window (MW).


## -prototype


````
NDK_FN_GET_REMOTE_TOKEN_FROM_MW NdkGetRemoteTokenFromMw;

UINT32 NdkGetRemoteTokenFromMw(
  _In_ NDK_MW *pNdkMw
)
{ ... }
````


## -parameters




### -param *pNdkMw [in]

A pointer to an NDK memory window (MW) object (<a href="..\ndkpi\ns-ndkpi-_ndk_mw.md">NDK_MW</a>).


## -returns



The 
     <i>NdkGetRemoteTokenFromMw</i> function returns a remote memory region token.




## -remarks



 After an <i>NdkBind</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_bind.md">NDK_FN_BIND</a>) call returns control to the caller, <i>NdkGetRemoteTokenFromMw</i> can be called to retrieve the remote token.




## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_bind.md">NDK_FN_BIND</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_mw.md">NDK_MW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_REMOTE_TOKEN_FROM_MW callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

