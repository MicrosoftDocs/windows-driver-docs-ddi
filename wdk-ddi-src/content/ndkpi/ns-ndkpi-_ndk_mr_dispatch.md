---
UID: NS:ndkpi._NDK_MR_DISPATCH
title: _NDK_MR_DISPATCH (ndkpi.h)
description: The NDK_MR_DISPATCH structure specifies dispatch function entry points for the NDK memory region (MR) object.
old-location: netvista\ndk_mr_dispatch.htm
tech.root: netvista
ms.assetid: C0EC5488-B08D-40A6-9E90-48E59B45B116
ms.date: 05/02/2018
keywords: ["NDK_MR_DISPATCH structure"]
ms.keywords: NDK_MR_DISPATCH, NDK_MR_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_MR_DISPATCH, PNDK_MR_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_MR_DISPATCH, ndkpi/NDK_MR_DISPATCH, ndkpi/PNDK_MR_DISPATCH, netvista.ndk_mr_dispatch
f1_keywords:
 - "ndkpi/NDK_MR_DISPATCH"
 - "NDK_MR_DISPATCH"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndkpi.h
api_name:
- NDK_MR_DISPATCH
targetos: Windows
req.typenames: NDK_MR_DISPATCH
---

# _NDK_MR_DISPATCH structure


## -description


The <b>NDK_MR_DISPATCH</b> structure specifies dispatch function entry points for the NDK memory region (MR) object.


## -struct-fields




### -field NdkCloseMr

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkRegisterMr

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_register_mr">NDK_FN_REGISTER_MR</a> dispatch function.


### -field NdkDeregisterMr

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_deregister_mr">NDK_FN_DEREGISTER_MR</a> dispatch function.


### -field NdkInitializeFastRegisterMr

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_initialize_fast_register_mr">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a> dispatch function.


### -field NdkGetRemoteTokenFromMr

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_remote_token_from_mr">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a> dispatch function.


### -field NdkGetLocalTokenFromMr

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_local_token_from_mr">NDK_FN_GET_LOCAL_TOKEN_FROM_MR</a> dispatch function.


## -remarks



The <b>NDK_MR_DISPATCH</b> structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_deregister_mr">NDK_FN_DEREGISTER_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_local_token_from_mr">NDK_FN_GET_LOCAL_TOKEN_FROM_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_remote_token_from_mr">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_initialize_fast_register_mr">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_register_mr">NDK_FN_REGISTER_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>
 

 

