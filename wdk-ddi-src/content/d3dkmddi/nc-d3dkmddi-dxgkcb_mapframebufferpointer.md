---
UID: NC:d3dkmddi.DXGKCB_MAPFRAMEBUFFERPOINTER
title: DXGKCB_MAPFRAMEBUFFERPOINTER (d3dkmddi.h)
description: DXGKCB_MAPFRAMEBUFFERPOINTER obtains a pointer to a subregion of the section object that was created for each physical adapter.
ms.date: 10/13/2021
keywords: ["DXGKCB_MAPFRAMEBUFFERPOINTER callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
f1_keywords:
 - DXGKCB_MAPFRAMEBUFFERPOINTER
 - d3dkmddi/DXGKCB_MAPFRAMEBUFFERPOINTER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_MAPFRAMEBUFFERPOINTER
product:
 - Windows
---

# DXGKCB_MAPFRAMEBUFFERPOINTER callback function

## -description

**DXGKCB_MAPFRAMEBUFFERPOINTER** obtains a pointer to a subregion of the section object that was created for each physical adapter.

## -parameters

### -param hAdapter

[in] A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pMapFrameBufferPointer

[in/out] Pointer to [**DXGKARGCB_MAPFRAMEBUFFERPOINTER**](ns-d3dkmddi-_dxgkargcb_mapframebufferpointer.md) structure that contains a pointer to the subregion of the section object.

## -returns

**DXGKCB_MAPFRAMEBUFFERPOINTER** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_MAPFRAMEBUFFERPOINTER**](ns-d3dkmddi-_dxgkargcb_mapframebufferpointer.md) and then call **DxgkCbMapFrameBufferPointer** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_UNMAPFRAMEBUFFERPOINTER**](nc-d3dkmddi-dxgkcb_unmapframebufferpointer.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
