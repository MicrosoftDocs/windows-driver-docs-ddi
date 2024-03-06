---
UID: NS:d3dkmddi._DXGKARGCB_MAPMDLTOIOMMU
title: DXGKARGCB_MAPMDLTOIOMMU (d3dkmddi.h)
description: The DXGKARGCB_MAPMDLTOIOMMU structure contains the arguments used by the DXGKCB_MAPMDLTOIOMMU callback function, to map a memory descriptor list (MDL) to the IOMMU.
ms.date: 10/13/2021
keywords: ["DXGKARGCB_MAPMDLTOIOMMU structure"]
ms.keywords: _DXGKARGCB_MAPMDLTOIOMMU, DXGKARGCB_MAPMDLTOIOMMU, *INOUT_PDXGKARGCB_MAPMDLTOIOMMU
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARGCB_MAPMDLTOIOMMU
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_MAPMDLTOIOMMU
 - d3dkmddi/_DXGKARGCB_MAPMDLTOIOMMU
 - DXGKARGCB_MAPMDLTOIOMMU
 - d3dkmddi/DXGKARGCB_MAPMDLTOIOMMU
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_MAPMDLTOIOMMU
 - DXGKARGCB_MAPMDLTOIOMMU
---

# DXGKARGCB_MAPMDLTOIOMMU structure

## -description

The **DXGKARGCB_MAPMDLTOIOMMU** structure contains the arguments used by the [**DXGKCB_MAPMDLTOIOMMU**](nc-d3dkmddi-dxgkcb_mapmdltoiommu.md) callback function, to map a memory descriptor list (MDL) to the IOMMU.

## -struct-fields

### -field pMdl [in]

An MDL which must be populated with valid pages. The MDL and the pages it points to must remain unchanged until the corresponding unmap call is made.

### -field hMemoryHandle [out]

A *Dxgkrnl* tracking handle for the allocation. This value should be passed to the corresponding [**DXGKCB_UNMAPMDLFROMIOMMU**](nc-d3dkmddi-dxgkcb_unmapmdlfromiommu.md) function.

## -remarks

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_MAPMDLTOIOMMU**](nc-d3dkmddi-dxgkcb_mapmdltoiommu.md)
