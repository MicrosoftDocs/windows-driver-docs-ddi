---
UID: NS:ndkpi._NDK_SRQ_DISPATCH
title: _NDK_SRQ_DISPATCH (ndkpi.h)
description: The NDK_SRQ_DISPATCH structure specifies dispatch function entry points for the NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_srq_dispatch.htm
tech.root: netvista
ms.assetid: 13297898-A72B-4771-A022-FDCBC281CEA0
ms.date: 05/02/2018
keywords: ["_NDK_SRQ_DISPATCH structure"]
ms.keywords: NDK_SRQ_DISPATCH, NDK_SRQ_DISPATCH structure [Network Drivers Starting with Windows Vista], _NDK_SRQ_DISPATCH, ndkpi/NDK_SRQ_DISPATCH, netvista.ndk_srq_dispatch
f1_keywords:
 - "ndkpi/NDK_SRQ_DISPATCH"
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
- NDK_SRQ_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# _NDK_SRQ_DISPATCH structure


## -description


The <b>NDK_SRQ_DISPATCH</b> structure specifies dispatch function entry points for the NDK shared receive queue (SRQ) object.


## -struct-fields




### -field NdkCloseSrq

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkModifySrq

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_modify_srq">NDK_FN_MODIFY_SRQ</a> dispatch function.


### -field NdkSrqReceive

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_srq_receive">NDK_FN_SRQ_RECEIVE</a> dispatch function.


## -remarks



The <b>NDK_SRQ_DISPATCH</b> structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq">NDK_SRQ</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_modify_srq">NDK_FN_MODIFY_SRQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_srq_receive">NDK_FN_SRQ_RECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq">NDK_SRQ</a>
 

 

