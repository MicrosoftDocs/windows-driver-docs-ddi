---
UID: NS:ndkpi._NDK_CQ_DISPATCH
title: _NDK_CQ_DISPATCH (ndkpi.h)
description: The NDK_CQ_DISPATCH structure specifies dispatch function entry points for the NDK completion queue (CQ) object.
old-location: netvista\ndk_cq_dispatch.htm
tech.root: netvista
ms.assetid: 632E4FE8-BA03-4232-80E1-5EB3CC760D14
ms.date: 05/02/2018
keywords: ["_NDK_CQ_DISPATCH structure"]
ms.keywords: NDK_CQ_DISPATCH, NDK_CQ_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_CQ_DISPATCH, PNDK_CQ_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_CQ_DISPATCH, ndkpi/NDK_CQ_DISPATCH, ndkpi/PNDK_CQ_DISPATCH, netvista.ndk_cq_dispatch
f1_keywords:
 - "ndkpi/NDK_CQ_DISPATCH"
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
- NDK_CQ_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: NDK_CQ_DISPATCH
---

# _NDK_CQ_DISPATCH structure


## -description


The <b>NDK_CQ_DISPATCH</b> structure specifies dispatch function entry points for the NDK completion queue (CQ) object.


## -struct-fields




### -field NdkCloseCq

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkResizeCq

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_resize_cq">NDK_FN_RESIZE_CQ</a> dispatch function.


### -field NdkArmCq

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_arm_cq">NDK_FN_ARM_CQ</a> dispatch function.


### -field NdkGetCqResults

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_cq_results">NDK_FN_GET_CQ_RESULTS</a> dispatch function.


### -field NdkControlCqInterruptModeration

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_control_cq_interrupt_moderation">NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</a> dispatch function.


### -field NdkGetCqResultsEx

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_cq_results_ex">NDK_FN_GET_CQ_RESULTS_EX</a> dispatch function. 

<b>Note</b>  This member is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.


## -remarks



The <b>NDK_CQ_DISPATCH</b> structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_arm_cq">NDK_FN_ARM_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_control_cq_interrupt_moderation">NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_cq_results">NDK_FN_GET_CQ_RESULTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_resize_cq">NDK_FN_RESIZE_CQ</a>
 

 

