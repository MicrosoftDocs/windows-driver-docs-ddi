---
UID: NS:ndkpi._NDK_EXTENSION_INTERFACE
title: _NDK_EXTENSION_INTERFACE (ndkpi.h)
description: The NDK_EXTENSION_INTERFACE structure specifies dispatch function entry points for an NDK extension interface.
old-location: netvista\ndk_extension_interface.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_EXTENSION_INTERFACE structure"]
ms.keywords: NDK_EXTENSION_INTERFACE, NDK_EXTENSION_INTERFACE structure [Network Drivers Starting with Windows Vista], PNDK_EXTENSION_INTERFACE, PNDK_EXTENSION_INTERFACE structure pointer [Network Drivers Starting with Windows Vista], _NDK_EXTENSION_INTERFACE, ndkpi/NDK_EXTENSION_INTERFACE, ndkpi/PNDK_EXTENSION_INTERFACE, netvista.ndk_extension_interface
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
req.typenames: NDK_EXTENSION_INTERFACE
f1_keywords:
 - _NDK_EXTENSION_INTERFACE
 - ndkpi/_NDK_EXTENSION_INTERFACE
 - NDK_EXTENSION_INTERFACE
 - ndkpi/NDK_EXTENSION_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - _NDK_EXTENSION_INTERFACE
 - NDK_EXTENSION_INTERFACE
---

# _NDK_EXTENSION_INTERFACE structure


## -description

The <b>NDK_EXTENSION_INTERFACE</b> structure specifies dispatch function entry points for an NDK extension interface.

## -struct-fields

### -field Dispatch

An entry point for an extension interface dispatch function.

## -remarks

An extension interface is identified by a GUID and represented as a pointer to an <b>NDK_EXTENSION_INTERFACE</b> function dispatch table.

Each NDK object contains a <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> function pointer in its object type-specific function dispatch table. This function allows a driver to query the extended interfaces the object type supports.

<div class="alert"><b>Tip</b>   There are currently no standard extension interfaces defined.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>

