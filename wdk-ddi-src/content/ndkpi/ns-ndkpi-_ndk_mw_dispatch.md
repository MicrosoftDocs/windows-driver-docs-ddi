---
UID: NS:ndkpi._NDK_MW_DISPATCH
title: _NDK_MW_DISPATCH (ndkpi.h)
description: The NDK_MW_DISPATCH structure specifies dispatch function entry points for the NDK memory window (MW) object.
old-location: netvista\ndk_mw_dispatch.htm
tech.root: netvista
ms.assetid: B35BDBBC-C8AB-4837-8637-30BA2E31831C
ms.date: 05/02/2018
keywords: ["NDK_MW_DISPATCH structure"]
ms.keywords: NDK_MW_DISPATCH, NDK_MW_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_MW_DISPATCH, PNDK_MW_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_MW_DISPATCH, ndkpi/NDK_MW_DISPATCH, ndkpi/PNDK_MW_DISPATCH, netvista.ndk_mw_dispatch
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
targetos: Windows
req.typenames: NDK_MW_DISPATCH
f1_keywords:
 - _NDK_MW_DISPATCH
 - ndkpi/_NDK_MW_DISPATCH
 - NDK_MW_DISPATCH
 - ndkpi/NDK_MW_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - NDK_MW_DISPATCH
---

# _NDK_MW_DISPATCH structure


## -description

The <b>NDK_MW_DISPATCH</b> structure specifies dispatch function entry points for the NDK memory window (MW) object.

## -struct-fields

### -field NdkCloseMw

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a> dispatch function.

### -field NdkQueryExtension

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.

### -field NdkGetRemoteTokenFromMw

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_remote_token_from_mw">NDK_FN_GET_REMOTE_TOKEN_FROM_MW</a> dispatch function.

## -remarks

The <b>NDK_MW_DISPATCH</b> structure is used in the <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mw">NDK_MW</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_remote_token_from_mw">NDK_FN_GET_REMOTE_TOKEN_FROM_MW</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mw">NDK_MW</a>