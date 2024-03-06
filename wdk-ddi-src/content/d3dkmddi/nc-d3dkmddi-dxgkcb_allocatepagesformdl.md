---
UID: NC:d3dkmddi.DXGKCB_ALLOCATEPAGESFORMDL
title: DXGKCB_ALLOCATEPAGESFORMDL (d3dkmddi.h)
description: DXGKCB_ALLOCATEPAGESFORMDL allocates physical memory pages for a memory descriptor list (MDL) to be mapped to the IOMMU's logical address space.
ms.date: 10/13/2021
keywords: ["DXGKCB_ALLOCATEPAGESFORMDL callback function"]
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
 - DXGKCB_ALLOCATEPAGESFORMDL
 - d3dkmddi/DXGKCB_ALLOCATEPAGESFORMDL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_ALLOCATEPAGESFORMDL
---

# DXGKCB_ALLOCATEPAGESFORMDL callback function

## -description

**DXGKCB_ALLOCATEPAGESFORMDL** allocates physical memory pages for a memory descriptor list (MDL) to be mapped to the IOMMU's logical address space.

## -parameters

### -param hAdapter [in]

A handle to the display adapter.

### -param pAllocatePagesForMdl [in/out]

Pointer to a [**DXGKARGCB_ALLOCATEPAGESFORMDL**](ns-d3dkmddi-_dxgkargcb_allocatepagesformdl.md) structure that contains arguments to allocate pages for MDL.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS error code.

## -remarks

This callback function is a Windows graphics port driver function equivalent to the [**MmAllocatePagesForMdl** function](../wdm/nf-wdm-mmallocatepagesformdl.md).

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_ALLOCATEPAGESFORMDL**](ns-d3dkmddi-_dxgkargcb_allocatepagesformdl.md) and then call **DxgkCbAllocatePagesForMdl** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

All memory accessed by the GPU during paging operations, or mapped via the GpuMmu must be mapped to the IOMMU. *Dxgkrnl* provides callbacks to the kernel-mode driver to allow the allocation and remapping in one step.

> [!NOTE]
> Calls to **DXGKCB_ALLOCATEPAGESFORMDL** are limited to the 4GB PAGE_SIZE MDL restriction, and *Dxgkrnl* always specifies the **MM_ALLOCATE_FULLY_REQUIRED** flag in the internal call to [**MmAllocatePagesForMdlEx** function](../wdm/nf-wdm-mmallocatepagesformdl.md). The driver should also not lock any memory. *Dxgkrnl* will manage locked pages for the driver, and once the memory is remapped, the logical address of the pages provided to the driver may no longer match the physical addresses.

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKARGCB_ALLOCATEPAGESFORMDL**](ns-d3dkmddi-_dxgkargcb_allocatepagesformdl.md)

[**DXGKCB_FREEPAGESFROMMDL**](nc-d3dkmddi-dxgkcb_freepagesfrommdl.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
