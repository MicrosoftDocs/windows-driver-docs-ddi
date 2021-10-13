---
UID: NC:d3dkmddi.DXGKCB_ALLOCATECONTIGUOUSMEMORY
title: DXGKCB_ALLOCATECONTIGUOUSMEMORY (d3dkmddi.h)
description: DXGKCB_ALLOCATECONTIGUOUSMEMORY allocates contiguous memory regions in the IOMMU's logical address space.
ms.date: 10/13/2021
keywords: ["DXGKCB_ALLOCATECONTIGUOUSMEMORY callback function"]
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
 - DXGKCB_ALLOCATECONTIGUOUSMEMORY
 - d3dkmddi/DXGKCB_ALLOCATECONTIGUOUSMEMORY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_ALLOCATECONTIGUOUSMEMORY
product:
 - Windows
---

# DXGKCB_ALLOCATECONTIGUOUSMEMORY callback function

## -description

**DXGKCB_ALLOCATECONTIGUOUSMEMORY** allocates contiguous memory regions in the IOMMU's logical address space.

## -parameters

### -param hAdapter

[in] Handle to a display adapter.

### -param pAllocateContiguousMemory

[in/out] Pointer to a [**DXGKARGCB_ALLOCATECONTIGUOUSMEMORY**](ns-d3dkmddi-_dxgkargcb_allocatecontiguousmemory.md) structure that contains arguments to allocate contiguous memory.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS error code.

## -remarks

 This callback function is *Dxgkrnl*'s equivalent to the [**MmAllocateContiguousMemory** function](../wdm/nf-wdm-mmallocatecontiguousmemory.md).

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_ALLOCATECONTIGUOUSMEMORY**](ns-d3dkmddi-_dxgkargcb_allocatecontiguousmemory.md) and then call **DxgkCbAllocateContiguousMemory** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

All memory accessed by the GPU during paging operations, or mapped via the GpuMmu must be mapped to the IOMMU. The *Dxgkrnl* provides callbacks to the KMD to allow the allocation and remapping in one step.

> [!NOTE]
> The driver should not lock any memory. *Dxgkrnl* will manage locked pages for the driver, and once the memory is remapped, the logical address of the pages provided to the driver may no longer match the physical addresses.

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKARGCB_ALLOCATECONTIGUOUSMEMORY**](ns-d3dkmddi-_dxgkargcb_allocatecontiguousmemory.md)

[**DXGKCB_FREECONTIGUOUSMEMORY**](ns-d3dkmddi-_dxgkargcb_freecontiguousmemory.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
