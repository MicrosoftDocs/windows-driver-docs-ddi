---
UID: NS:ndkpi._NDK_CONNECTOR
title: _NDK_CONNECTOR (ndkpi.h)
description: The NDK_CONNECTOR structure specifies the attributes of an NDK connector object.
old-location: netvista\ndk_connector.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_CONNECTOR structure"]
ms.keywords: NDK_CONNECTOR, NDK_CONNECTOR structure [Network Drivers Starting with Windows Vista], PNDK_CONNECTOR, PNDK_CONNECTOR structure pointer [Network Drivers Starting with Windows Vista], _NDK_CONNECTOR, ndkpi/NDK_CONNECTOR, ndkpi/PNDK_CONNECTOR, netvista.ndk_connector
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
req.typenames: NDK_CONNECTOR
f1_keywords:
 - _NDK_CONNECTOR
 - ndkpi/_NDK_CONNECTOR
 - NDK_CONNECTOR
 - ndkpi/NDK_CONNECTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - _NDK_CONNECTOR
 - NDK_CONNECTOR
---

# _NDK_CONNECTOR structure


## -description

The <b>NDK_CONNECTOR</b> structure specifies the attributes of an NDK connector object.

## -struct-fields

### -field Header

The <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> structure for the <b>NDK_CONNECTOR</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeConnector</b>.

### -field Dispatch

A pointer to an <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a> structure that defines dispatch functions for the NDK connector object.

## -remarks

An NDK provider must set the <b>Dispatch</b> member pointer to its  <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a> table before returning the created connector object. The provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can set the <b>Dispatch</b> member to some other value.

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-listeners--connectors--and-endpoints">NDKPI Listeners, Connectors, and Endpoints</a>



<a href="/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_connector">NDK_FN_CREATE_CONNECTOR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>

