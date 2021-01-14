---
UID: NS:ndkpi._NDK_MR
title: _NDK_MR (ndkpi.h)
description: The NDK_MR structure specifies the attributes of an NDK memory region (MR) object.
old-location: netvista\ndk_mr.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_MR structure"]
ms.keywords: NDK_MR, NDK_MR structure [Network Drivers Starting with Windows Vista], PNDK_MR, PNDK_MR structure pointer [Network Drivers Starting with Windows Vista], _NDK_MR, ndkpi/NDK_MR, ndkpi/PNDK_MR, netvista.ndk_mr
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
req.typenames: NDK_MR
f1_keywords:
 - _NDK_MR
 - ndkpi/_NDK_MR
 - NDK_MR
 - ndkpi/NDK_MR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - _NDK_MR
 - NDK_MR
---

# _NDK_MR structure


## -description

The <b>NDK_MR</b> structure specifies the attributes of an NDK memory region (MR) object.

## -struct-fields

### -field Header

The <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> structure for the <b>NDK_MR</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeMr</b>.

### -field Dispatch

A pointer to an <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr_dispatch">NDK_MR_DISPATCH</a> structure that defines dispatch functions for the NDK MR object.

## -remarks

An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr_dispatch">NDK_MR_DISPATCH</a> table before returning the  created MR object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_mr">NDK_FN_CREATE_MR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr_dispatch">NDK_MR_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>

