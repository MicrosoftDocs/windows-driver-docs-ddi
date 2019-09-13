---
UID: NC:d3dkmddi.DXGKCB_UNMAPMDLFROMIOMMU
title: DXGKCB_UNMAPMDLFROMIOMMU (d3dkmddi.h)
description: Implemented by the client driver to release the mapping that was set by DXGKCB_MAPMDLTOIOMMU.
ms.assetid: 1b2a9208-b16c-4fe2-a3be-5102a6b2676e
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
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
 - "d3dkmddi/DXGKCB_UNMAPMDLFROMIOMMU"
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

Implemented by the client driver to release the mapping that was set by [DXGKCB_MAPMDLTOIOMMU](nc-d3dkmddi-dxgkcb_mapmdltoiommu.md).

## -parameters

### -param hAdapter

A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pUnmapMdlFromIoMmu

A pointer to the [DXGKARGCB_UNMAPMDLFROMIOMMU](ns-d3dkmddi-_dxgkargcb_unmapmdlfromiommu.md) structure that contains a handle to the memory to be unmapped.

## -returns

This callback function does not return a value.

## -prototype

```cpp
//Declaration

DXGKCB_UNMAPMDLFROMIOMMU DxgkcbUnmapmdlfromiommu;

// Definition

VOID DxgkcbUnmapmdlfromiommu
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARGCB_UNMAPMDLFROMIOMMU pUnmapMdlFromIoMmu
)
{...}

DXGKCB_UNMAPMDLFROMIOMMU


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARGCB_UNMAPMDLFROMIOMMU and then calling DxgkCbUnmapMdlFromIoMmu.

## -see-also

