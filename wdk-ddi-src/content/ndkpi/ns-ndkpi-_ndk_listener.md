---
UID: NS:ndkpi._NDK_LISTENER
title: _NDK_LISTENER (ndkpi.h)
description: The NDK_LISTENER structure specifies the attributes of an NDK listener object.
old-location: netvista\ndk_listener.htm
tech.root: netvista
ms.assetid: 0043DC3F-E8EE-448F-B381-C67C199CE7A7
ms.date: 05/02/2018
keywords: ["NDK_LISTENER structure"]
ms.keywords: NDK_LISTENER, NDK_LISTENER structure [Network Drivers Starting with Windows Vista], PNDK_LISTENER, PNDK_LISTENER structure pointer [Network Drivers Starting with Windows Vista], _NDK_LISTENER, ndkpi/NDK_LISTENER, ndkpi/PNDK_LISTENER, netvista.ndk_listener
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
req.typenames: NDK_LISTENER
f1_keywords:
 - _NDK_LISTENER
 - ndkpi/_NDK_LISTENER
 - NDK_LISTENER
 - ndkpi/NDK_LISTENER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - NDK_LISTENER
---

# _NDK_LISTENER structure


## -description

The <b>NDK_LISTENER</b> structure specifies the attributes of an NDK listener object.

## -struct-fields

### -field Header

The <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> structure for the <b>NDK_LISTENER</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeListener</b>.

### -field Dispatch

A pointer to an <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_listener_dispatch">NDK_LISTENER_DISPATCH</a> structure that defines dispatch functions for the NDK listener object.

## -remarks

An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_listener_dispatch">NDK_LISTENER_DISPATCH</a> table before returning the  created listener object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-listeners--connectors--and-endpoints">NDKPI Listeners, Connectors, and Endpoints</a>



<a href="/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener">NDK_FN_CREATE_LISTENER</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_listener_dispatch">NDK_LISTENER_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>