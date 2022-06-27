---
UID: NC:d3dkmddi.DXGKCB_RELEASEHANDLEDATA
title: DXGKCB_RELEASEHANDLEDATA (d3dkmddi.h)
description: Releases handle data.
ms.date: 05/24/2022
keywords: ["DXGKCB_RELEASEHANDLEDATA callback function"]
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
 - DXGKCB_RELEASEHANDLEDATA
 - d3dkmddi/DXGKCB_RELEASEHANDLEDATA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_RELEASEHANDLEDATA
dev_langs:
 - c++
---

# DXGKCB_RELEASEHANDLEDATA callback function

## -description

**DXGKCB_RELEASEHANDLEDATA** releases a reference to an allocation.

## -parameters

### -param unnamedParam1 [in]

A [**DXGKARGCB_RELEASEHANDLEDATA**](ns-d3dkmddi-dxgkargcb_releasehandledata.md) structure containing information about the allocation to be released.

## -remarks

The allocation reference was acquired in a prior call to [**DXGKCB_ACQUIREHANDLEDATA**](nc-d3dkmddi-dxgkcb_acquirehandledata.md).

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_RELEASEHANDLEDATA**](ns-d3dkmddi-dxgkargcb_releasehandledata.md) and then call **DxgkCbReleaseHandleData** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_RELEASEHANDLEDATA**](ns-d3dkmddi-dxgkargcb_releasehandledata.md)

[**DXGKCB_ACQUIREHANDLEDATA**](nc-d3dkmddi-dxgkcb_acquirehandledata.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
