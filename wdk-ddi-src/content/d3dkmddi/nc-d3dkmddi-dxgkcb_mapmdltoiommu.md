---
UID: NC:d3dkmddi.DXGKCB_MAPMDLTOIOMMU
title: DXGKCB_MAPMDLTOIOMMU (d3dkmddi.h)
description: DXGKCB_MAPMDLTOIOMMU maps a memory descriptor list (MDL) to the IOMMU so that the underlying memory can be accessed by the GPU.
ms.date: 10/13/2021
keywords: ["DXGKCB_MAPMDLTOIOMMU callback function"]
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
 - DXGKCB_MAPMDLTOIOMMU
 - d3dkmddi/DXGKCB_MAPMDLTOIOMMU
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_MAPMDLTOIOMMU
---

# DXGKCB_MAPMDLTOIOMMU callback function

## -description

A kernel-mode display miniport driver calls **DXGKCB_MAPMDLTOIOMMU** to map a memory descriptor list (MDL) to the IOMMU so that the underlying memory can be accessed by the GPU.

## -parameters

### -param hAdapter [in]

A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pMapMdlToIoMmu [in/out]

Pointer to a [**DXGKARGCB_MAPMDLTOIOMMU**](ns-d3dkmddi-_dxgkargcb_mapmdltoiommu.md) structure that contains a handle to the memory.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate member of [DXGKARGCB_MAPMDLTOIOMMU](ns-d3dkmddi-_dxgkargcb_mapmdltoiommu.md) and then call **DxgkCbMapMdlToIoMmu** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

If the driver uses this callback, it is responsible for ensuring that the lifetime of the MDL exceeds the corresponding [**DXGKCB_UNMAPMDLFROMIOMMU**](nc-d3dkmddi-dxgkcb_unmapmdlfromiommu.md) call. Otherwise the **DXGKCB_UNMAPMDLFROMIOMMU** call has undefined behavior and may lead to compromised security of the pages from the MDL. The pages could get repurposed by Mm by the time they are unmapped.

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[DXGKARGCB_MAPMDLTOIOMMU](ns-d3dkmddi-_dxgkargcb_mapmdltoiommu.md)

[**DXGKCB_UNMAPMDLFROMIOMMU**](nc-d3dkmddi-dxgkcb_unmapmdlfromiommu.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
