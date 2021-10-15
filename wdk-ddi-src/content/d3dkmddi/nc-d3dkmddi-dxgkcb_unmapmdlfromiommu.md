---
UID: NC:d3dkmddi.DXGKCB_UNMAPMDLFROMIOMMU
title: DXGKCB_UNMAPMDLFROMIOMMU (d3dkmddi.h)
description: DXGKCB_UNMAPMDLFROMIOMMU releases the mapping that was set by DXGKCB_MAPMDLTOIOMMU.
ms.date: 10/13/2021
keywords: ["DXGKCB_UNMAPMDLFROMIOMMU callback function"]
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
 - DXGKCB_UNMAPMDLFROMIOMMU
 - d3dkmddi/DXGKCB_UNMAPMDLFROMIOMMU
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_UNMAPMDLFROMIOMMU
product:
 - Windows
---

# DXGKCB_UNMAPMDLFROMIOMMU callback function

## -description

**DXGKCB_UNMAPMDLFROMIOMMU** releases the mapping that was set by [**DXGKCB_MAPMDLTOIOMMU**](nc-d3dkmddi-dxgkcb_mapmdltoiommu.md).

## -parameters

### -param hAdapter

[in] A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pUnmapMdlFromIoMmu

[in] A pointer to the [**DXGKARGCB_UNMAPMDLFROMIOMMU**](ns-d3dkmddi-_dxgkargcb_unmapmdlfromiommu.md) structure that contains a handle to the memory to be unmapped.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_UNMAPMDLFROMIOMMU**](ns-d3dkmddi-_dxgkargcb_unmapmdlfromiommu.md) and then calls **DxgkCbUnmapMdlFromIoMmu** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKARGCB_UNMAPMDLFROMIOMMU**](ns-d3dkmddi-_dxgkargcb_unmapmdlfromiommu.md)

[**DXGKCB_MAPMDLTOIOMMU**](nc-d3dkmddi-dxgkcb_mapmdltoiommu.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
