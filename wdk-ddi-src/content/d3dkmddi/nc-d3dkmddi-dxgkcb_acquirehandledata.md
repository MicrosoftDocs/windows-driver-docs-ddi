---
UID: NC:d3dkmddi.DXGKCB_ACQUIREHANDLEDATA
title: DXGKCB_ACQUIREHANDLEDATA (d3dkmddi.h)
description: Acquires a resource handle.
ms.date: 10/13/2021
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

**DXGKCB_ACQUIREHANDLEDATA** acquires a reference to an allocation.

## -parameters

### -param unnamedParam1 [in]

Pointer to a [**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md) structure that describes an allocation handle returned by [**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md).

## -param Arg2

[out] Pointer to a release handle for the driver to use when releasing the allocation reference.

## -returns

None.

## -remarks

Allocation handles can be destroyed at any time by an application or by a user-mode driver call to [**D3DKMTDestroyAllocation**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation.md) on a valid handle. Allocation destruction involves a request to the kernel-mode driver to delete the allocation object that *Dxgkrnl* returned to them during allocation creation, so the KMD could end up with a stale pointer to freed memory. **DXGKCB_ACQUIREHANDLEDATA** and [**DXGKCB_RELEASEHANDLEDATA**](nc-d3dkmddi-dxgkcb_releasehandledata.md) allow the driver to hold a reference on the *Dxgkrnl* object and ensure that *Dxgkrnl* does not destroy the allocation and the KMD-associated objects until after the release call is made.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md) and then call **DxgkCbAcquireHandleData** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md)

[**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md)

[**DXGKCB_RELEASEHANDLEDATA**](nc-d3dkmddi-dxgkcb_releasehandledata.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
