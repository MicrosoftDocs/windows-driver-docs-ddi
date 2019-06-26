---
UID: NS:ndkpi._NDK_SHARED_ENDPOINT_DISPATCH
title: _NDK_SHARED_ENDPOINT_DISPATCH (ndkpi.h)
description: The NDK_SHARED_ENDPOINT_DISPATCH structure specifies dispatch function entry points for the NDK shared endpoint object.
old-location: netvista\ndk_shared_endpoint_dispatch.htm
tech.root: netvista
ms.assetid: A0AFCF2B-E1A9-478C-8B03-D7C873F83369
ms.date: 05/02/2018
ms.keywords: NDK_SHARED_ENDPOINT_DISPATCH, NDK_SHARED_ENDPOINT_DISPATCH structure [Network Drivers Starting with Windows Vista], _NDK_SHARED_ENDPOINT_DISPATCH, ndkpi/NDK_SHARED_ENDPOINT_DISPATCH, netvista.ndk_shared_endpoint_dispatch
ms.topic: struct
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
- NDK_SHARED_ENDPOINT_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: NDK_SHARED_ENDPOINT_DISPATCH
---

# _NDK_SHARED_ENDPOINT_DISPATCH structure


## -description


The <b>NDK_SHARED_ENDPOINT_DISPATCH</b> structure specifies dispatch function entry points for the NDK shared endpoint object.


## -struct-fields




### -field NdkCloseSharedEndpoint

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkGetLocalAddress

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_get_shared_endpoint_local_address">NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS</a> dispatch function.


## -remarks



The <b>NDK_SHARED_ENDPOINT_DISPATCH</b> structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_get_shared_endpoint_local_address">NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a>
 

 

