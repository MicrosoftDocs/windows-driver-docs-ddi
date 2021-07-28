---
UID: NS:d3dkmddi._DXGKARGCB_UNMAPMDLFROMIOMMU
title: DXGKARGCB_UNMAPMDLFROMIOMMU (d3dkmddi.h)
description: The DXGKARGCB_UNMAPMDLFROMIOMMU structure contains the arguments used by the DXGKCB_UNMAPMDLFROMIOMMU callback function to release the mapping that was set by DXGKCB_MAPMDLTOIOMMU.
ms.date: 07/22/2021
keywords: ["DXGKARGCB_UNMAPMDLFROMIOMMU structure"]
ms.keywords: _DXGKARGCB_UNMAPMDLFROMIOMMU, DXGKARGCB_UNMAPMDLFROMIOMMU,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARGCB_UNMAPMDLFROMIOMMU
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_UNMAPMDLFROMIOMMU
 - d3dkmddi/_DXGKARGCB_UNMAPMDLFROMIOMMU
 - DXGKARGCB_UNMAPMDLFROMIOMMU
 - d3dkmddi/DXGKARGCB_UNMAPMDLFROMIOMMU
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_UNMAPMDLFROMIOMMU
 - DXGKARGCB_UNMAPMDLFROMIOMMU
product:
 - Windows
---

# DXGKARGCB_UNMAPMDLFROMIOMMU structure

## -description

The **DXGKARGCB_UNMAPMDLFROMIOMMU** structure contains the arguments used by the [**DXGKCB_UNMAPMDLFROMIOMMU**](nc-d3dkmddi-dxgkcb_unmapmdlfromiommu.md) callback function to release the mapping that was set by [**DXGKCB_MAPMDLTOIOMMU**](nc-d3dkmddi-dxgkcb_mapmdltoiommu.md).

## -struct-fields

### -field hMemoryHandle

[in] A *Dxgkrnl* tracking handle for the allocation to be released.

## -remarks

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[DXGKCB_UNMAPMDLFROMIOMMU](nc-d3dkmddi-dxgkcb_unmapmdlfromiommu.md)
