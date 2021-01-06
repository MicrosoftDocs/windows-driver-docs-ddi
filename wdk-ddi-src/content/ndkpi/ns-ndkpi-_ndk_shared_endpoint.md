---
UID: NS:ndkpi._NDK_SHARED_ENDPOINT
title: _NDK_SHARED_ENDPOINT (ndkpi.h)
description: The NDK_SHARED_ENDPOINT structure specifies the attributes of an NDK shared endpoint object.
old-location: netvista\ndk_shared_endpoint.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_SHARED_ENDPOINT structure"]
ms.keywords: NDK_SHARED_ENDPOINT, NDK_SHARED_ENDPOINT structure [Network Drivers Starting with Windows Vista], PNDK_SHARED_ENDPOINT, PNDK_SHARED_ENDPOINT structure pointer [Network Drivers Starting with Windows Vista], _NDK_SHARED_ENDPOINT, ndkpi/NDK_SHARED_ENDPOINT, ndkpi/PNDK_SHARED_ENDPOINT, netvista.ndk_shared_endpoint
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
req.typenames: NDK_SHARED_ENDPOINT
f1_keywords:
 - _NDK_SHARED_ENDPOINT
 - ndkpi/_NDK_SHARED_ENDPOINT
 - NDK_SHARED_ENDPOINT
 - ndkpi/NDK_SHARED_ENDPOINT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - NDK_SHARED_ENDPOINT
---

# _NDK_SHARED_ENDPOINT structure


## -description

The <b>NDK_SHARED_ENDPOINT</b> structure specifies the attributes of an NDK shared endpoint object.

## -struct-fields

### -field Header

The <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> structure for the <b>NDK_SHARED_ENDPOINT</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeSharedEndpoint</b>.

### -field Dispatch

A pointer to an <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_shared_endpoint_dispatch">NDK_SHARED_ENDPOINT_DISPATCH</a> structure that defines dispatch functions for the NDK shared endpoint object.

## -remarks

NDK provider must set the <b>Dispatch</b> member to its own <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_shared_endpoint_dispatch">NDK_SHARED_ENDPOINT_DISPATCH</a> table before returning a newly created Shared Endpoint object and must NOT use the <b>Dispatch</b> member any more (because the NDK consumer is free to set the <b>Dispatch</b> member to some other value).

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-listeners--connectors--and-endpoints">NDKPI Listeners, Connectors, and Endpoints</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_shared_endpoint">NDK_FN_CREATE_SHARED_ENDPOINT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_shared_endpoint_dispatch">NDK_SHARED_ENDPOINT_DISPATCH</a>
