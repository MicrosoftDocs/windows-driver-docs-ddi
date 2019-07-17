---
UID: NS:ndkpi._NDK_PD_DISPATCH
title: _NDK_PD_DISPATCH (ndkpi.h)
description: The NDK_PD_DISPATCH structure specifies dispatch function entry points for the NDK protection domain (PD) object.
old-location: netvista\ndk_pd_dispatch.htm
tech.root: netvista
ms.assetid: 3BAD6CF9-8DCD-470F-9C2E-C7C9C0B29ADA
ms.date: 05/02/2018
ms.keywords: NDK_PD_DISPATCH, NDK_PD_DISPATCH structure [Network Drivers Starting with Windows Vista], _NDK_PD_DISPATCH, ndkpi/NDK_PD_DISPATCH, netvista.ndk_pd_dispatch
ms.topic: struct
f1_keywords:
 - "ndkpi/NDK_PD_DISPATCH"
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
- NDK_PD_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: NDK_PD_DISPATCH
---

# _NDK_PD_DISPATCH structure


## -description


The <b>NDK_PD_DISPATCH</b> structure specifies dispatch function entry points for the NDK protection domain (PD) object.


## -struct-fields




### -field NdkClosePd

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkCreateMr

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_mr">NDK_FN_CREATE_MR</a> dispatch function.


### -field NdkCreateMw

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_mw">NDK_FN_CREATE_MW</a> dispatch function.


### -field NdkCreateSrq

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_srq">NDK_FN_CREATE_SRQ</a> dispatch function.


### -field NdkCreateQp

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_qp">NDK_FN_CREATE_QP</a> dispatch function.


### -field NdkCreateQpWithSrq

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_qp_with_srq">NDK_FN_CREATE_QP_WITH_SRQ</a> dispatch function.


### -field NdkGetPrivilegedMemoryRegionToken

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_get_privileged_memory_region_token">NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN</a> dispatch function.


## -remarks



The <b>NDK_PD_DISPATCH</b> structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_mr">NDK_FN_CREATE_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_mw">NDK_FN_CREATE_MW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_qp">NDK_FN_CREATE_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_qp_with_srq">NDK_FN_CREATE_QP_WITH_SRQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_srq">NDK_FN_CREATE_SRQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_get_privileged_memory_region_token">NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>
 

 

