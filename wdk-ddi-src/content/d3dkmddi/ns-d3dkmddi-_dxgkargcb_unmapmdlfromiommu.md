---
UID: NS:d3dkmddi._DXGKARGCB_UNMAPMDLFROMIOMMU
title: _DXGKARGCB_UNMAPMDLFROMIOMMU (d3dkmddi.h)
description: Arguments used by the DxgkcbUnmapmdlFromIommu callback function to release the mapping that was set by DXGKCB_MAPMDLTOIOMMU.
ms.assetid: 39dc2658-d3dc-43fa-a29d-806db351d4d7
ms.date: 10/19/2018
keywords: ["DXGKARGCB_UNMAPMDLFROMIOMMU structure"]
f1_keywords:
 - "d3dkmddi/_DXGKARGCB_UNMAPMDLFROMIOMMU"
 - "_DXGKARGCB_UNMAPMDLFROMIOMMU"
ms.keywords: _DXGKARGCB_UNMAPMDLFROMIOMMU, DXGKARGCB_UNMAPMDLFROMIOMMU,
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARGCB_UNMAPMDLFROMIOMMU
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGKARGCB_UNMAPMDLFROMIOMMU
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARGCB_UNMAPMDLFROMIOMMU structure

## -description

Arguments used by the [DxgkcbUnmapmdlFromIommu](nc-d3dkmddi-dxgkcb_unmapmdlfromiommu.md) callback function to release the mapping that was set by [DXGKCB_MAPMDLTOIOMMU](nc-d3dkmddi-dxgkcb_mapmdltoiommu.md).

## -struct-fields

### -field hMemoryHandle

A dxgkrnl tracking handle for the allocation.

## -remarks

## -see-also

[DxgkcbUnmapmdlFromIommu](nc-d3dkmddi-dxgkcb_unmapmdlfromiommu.md)
