---
UID: NS:ndkpi._NDK_ADAPTER_DISPATCH
title: _NDK_ADAPTER_DISPATCH (ndkpi.h)
description: The NDK_ADAPTER_DISPATCH structure specifies dispatch function entry points for the NDK adapter object.
old-location: netvista\ndk_adapter_dispatch.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_ADAPTER_DISPATCH structure"]
ms.keywords: NDK_ADAPTER_DISPATCH, NDK_ADAPTER_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_ADAPTER_DISPATCH, PNDK_ADAPTER_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_ADAPTER_DISPATCH, ndkpi/NDK_ADAPTER_DISPATCH, ndkpi/PNDK_ADAPTER_DISPATCH, netvista.ndk_adapter_dispatch
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
req.typenames: NDK_ADAPTER_DISPATCH
f1_keywords:
 - _NDK_ADAPTER_DISPATCH
 - ndkpi/_NDK_ADAPTER_DISPATCH
 - NDK_ADAPTER_DISPATCH
 - ndkpi/NDK_ADAPTER_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - NDK_ADAPTER_DISPATCH
---

# _NDK_ADAPTER_DISPATCH structure


## -description

The <b>NDK_ADAPTER_DISPATCH</b> structure specifies dispatch function entry points for the NDK adapter object.

## -struct-fields

### -field NdkQueryExtension

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.

### -field NdkQueryAdapterInfo

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_adapter_info">NDK_FN_QUERY_ADAPTER_INFO</a> dispatch function.

### -field NdkCreateCq

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_cq">NDK_FN_CREATE_CQ</a> dispatch function.

### -field NdkCreatePd

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_pd">NDK_FN_CREATE_PD</a> dispatch function.

### -field NdkCreateSharedEndpoint

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_shared_endpoint">NDK_FN_CREATE_SHARED_ENDPOINT</a> dispatch function.

### -field NdkCreateConnector

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_connector">NDK_FN_CREATE_CONNECTOR</a> dispatch function.

### -field NdkCreateListener

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener">NDK_FN_CREATE_LISTENER</a> dispatch function.

### -field NdkBuildLAM

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_build_lam">NDK_FN_BUILD_LAM</a> dispatch function.

### -field NdkReleaseLAM

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_release_lam">NDK_FN_RELEASE_LAM</a> dispatch function.

## -remarks

The <b>NDK_ADAPTER_DISPATCH</b> structure is used in the <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter">NDK_ADAPTER</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter">NDK_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_build_lam">NDK_FN_BUILD_LAM</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_connector">NDK_FN_CREATE_CONNECTOR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_cq">NDK_FN_CREATE_CQ</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener">NDK_FN_CREATE_LISTENER</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_pd">NDK_FN_CREATE_PD</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_shared_endpoint">NDK_FN_CREATE_SHARED_ENDPOINT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_adapter_info">NDK_FN_QUERY_ADAPTER_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_release_lam">NDK_FN_RELEASE_LAM</a>
