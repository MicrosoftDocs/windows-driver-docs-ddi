---
UID: NC:ndkpi.NDK_FN_GET_LOCAL_TOKEN_FROM_MR
title: NDK_FN_GET_LOCAL_TOKEN_FROM_MR
author: windows-driver-content
description: The NdkGetLocalTokenFromMr (NDK_FN_GET_LOCAL_TOKEN_FROM_MR) function gets a memory token from a local NDK memory region (MR).
old-location: netvista\ndk_fn_get_local_token_from_mr.htm
old-project: netvista
ms.assetid: 5578112B-1BB2-4130-BBCE-20025A0A609C
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_get_local_token_from_mr, NdkGetLocalTokenFromMr callback function [Network Drivers Starting with Windows Vista], NdkGetLocalTokenFromMr, NDK_FN_GET_LOCAL_TOKEN_FROM_MR, NDK_FN_GET_LOCAL_TOKEN_FROM_MR, ndkpi/NdkGetLocalTokenFromMr
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
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	ndkpi.h
apiname: 
-	NdkGetLocalTokenFromMr
product: Windows
targetos: Windows
req.typenames: *PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_GET_LOCAL_TOKEN_FROM_MR callback


## -description


The <i>NdkGetLocalTokenFromMr</i> (<i>NDK_FN_GET_LOCAL_TOKEN_FROM_MR</i>) function gets a memory token from a local NDK memory region (MR).


## -prototype


````
NDK_FN_GET_LOCAL_TOKEN_FROM_MR NdkGetLocalTokenFromMr;

UINT32 NdkGetLocalTokenFromMr(
  _In_ NDK_MR *pNdkMr
)
{ ... }
````


## -parameters




### -param *pNdkMr






#### - pNdkMr [in]

A pointer to an NDK memory region (MR) object (<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>).


## -returns


The 
     <i>NdkGetLocalTokenFromMr</i> function returns a local memory region token.



## -remarks


<i>NdkGetLocalTokenFromMr</i> returns a local memory region token.  <i>NdkGetLocalTokenFromMr</i> can be called after a call to  the  <i>NdkRegisterMr</i>  (<a href="..\ndkpi\nc-ndkpi-ndk_fn_register_mr.md">NDK_FN_REGISTER_MR</a>) function  or  <i>NdkInitializeFastRegisterMr</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_initialize_fast_register_mr.md">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>) function completes without errors.



## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_initialize_fast_register_mr.md">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_register_mr.md">NDK_FN_REGISTER_MR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_LOCAL_TOKEN_FROM_MR callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

