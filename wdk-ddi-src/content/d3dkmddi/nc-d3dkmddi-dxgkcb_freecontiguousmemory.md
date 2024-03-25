---
UID: NC:d3dkmddi.DXGKCB_FREECONTIGUOUSMEMORY
title: DXGKCB_FREECONTIGUOUSMEMORY (d3dkmddi.h)
description: DXGKCB_FREECONTIGUOUSMEMORY frees a range of physically contiguous memory that was allocated by DXGKCB_ALLOCATECONTIGUOUSMEMORY.
ms.date: 10/13/2021
keywords: ["DXGKCB_FREECONTIGUOUSMEMORY callback function"]
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
 - DXGKCB_FREECONTIGUOUSMEMORY
 - d3dkmddi/DXGKCB_FREECONTIGUOUSMEMORY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_FREECONTIGUOUSMEMORY
---

# DXGKCB_FREECONTIGUOUSMEMORY callback function

## -description

**DXGKCB_FREECONTIGUOUSMEMORY** frees a range of physically contiguous memory that was allocated by [**DXGKCB_ALLOCATECONTIGUOUSMEMORY**](nc-d3dkmddi-dxgkcb_allocatecontiguousmemory.md).

## -parameters

### -param hAdapter [in]

Handle to a display adapter.

### -param pFreeContiguousMemory [in]

Pointer to a [**DXGKARGCB_FREECONTIGUOUSMEMORY**](ns-d3dkmddi-_dxgkargcb_freecontiguousmemory.md) structure that contains a handle to the contiguous memory to be freed.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS error code.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_FREECONTIGUOUSMEMORY**](ns-d3dkmddi-_dxgkargcb_freecontiguousmemory.md) and then call **DxgkCbFreeContiguousMemory** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKARGCB_FREECONTIGUOUSMEMORY**](ns-d3dkmddi-_dxgkargcb_freecontiguousmemory.md)

[**DXGKCB_ALLOCATECONTIGUOUSMEMORY**](nc-d3dkmddi-dxgkcb_allocatecontiguousmemory.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
