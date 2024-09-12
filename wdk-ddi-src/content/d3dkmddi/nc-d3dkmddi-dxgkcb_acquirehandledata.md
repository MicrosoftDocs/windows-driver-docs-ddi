---
UID: NC:d3dkmddi.DXGKCB_ACQUIREHANDLEDATA
title: DXGKCB_ACQUIREHANDLEDATA (d3dkmddi.h)
description: Learn more about the DXGKCB_ACQUIREHANDLEDATA callback function.
ms.date: 07/01/2024
keywords: ["DXGKCB_ACQUIREHANDLEDATA callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - DXGKCB_ACQUIREHANDLEDATA
 - d3dkmddi/DXGKCB_ACQUIREHANDLEDATA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_ACQUIREHANDLEDATA
dev_langs:
 - c++
---

# DXGKCB_ACQUIREHANDLEDATA callback function

## -description

**DxgkcbAcquirehandledata** acquires a reference to an allocation.

## -parameters

### -param unnamedParam1 [in]

Pointer to a [**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md) structure that describes an allocation handle returned by [**DxgkcbCreatecontextallocation**](nc-d3dkmddi-dxgkcb_createcontextallocation.md).

## -param unnamedParam2 [out]

Pointer to a release handle for the kernel-mode driver (KMD) to manage the lifetime of the reference to acquired allocation. The KMD uses this handle when it calls [**DxgkcbReleasehandledata**](nc-d3dkmddi-dxgkcb_releasehandledata.md) to release the allocation reference.

## -returns

**DxgkcbAcquirehandledata** returns a handle to the allocation that the KMD requested a reference to. The KMD uses this handle for subsequent operations on the allocation or resource.

## -remarks

An application or user-mode driver can call [**D3DKMTDestroyAllocation**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation.md) at any time to destroy an allocation handle. Allocation destruction involves a request to the KMD to delete the allocation object that *Dxgkrnl* returned to them during allocation creation, so the KMD could end up with a stale pointer to freed memory. **DxgkcbAcquirehandledata** and [**DxgkcbReleasehandledata**](nc-d3dkmddi-dxgkcb_releasehandledata.md) allow the driver to hold a reference on the *Dxgkrnl* object and ensure that *Dxgkrnl* doesn't destroy the allocation and the KMD-associated objects until after the release call is made.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md) and then call **DxgkCbAcquireHandleData** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md)

[**DxgkcbCreatecontextallocation**](nc-d3dkmddi-dxgkcb_createcontextallocation.md)

[**DxgkcbReleasehandledata**](nc-d3dkmddi-dxgkcb_releasehandledata.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
