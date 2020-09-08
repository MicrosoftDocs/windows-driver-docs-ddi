---
UID: NC:d3dkmddi.DXGKCB_MAPMDLTOIOMMU
title: DXGKCB_MAPMDLTOIOMMU (d3dkmddi.h)
description: Implemented by the client driver to map physical pages described by a memory descriptor list (MDL) into the system virtual address space, and use them with the IoMmu.
ms.assetid: 8badbe56-f46c-442c-8918-5e99db889278
ms.date: 10/19/2018
keywords: ["DXGKCB_MAPMDLTOIOMMU callback function"]
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
product:
 - Windows
---

# DXGKCB_MAPMDLTOIOMMU callback function


## -description

Implemented by the client driver to map physical pages described by a memory descriptor list (MDL) into the system virtual address space, and use them with the IoMmu.
This callback function is generally used to allocate memory that can't be allocated through one of the other allocation callbacks.

## -parameters

### -param hAdapter

A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pMapMdlToIoMmu

Pointer to a [DXGKARGCB_MAPMDLTOIOMMU](ns-d3dkmddi-_dxgkargcb_mapmdltoiommu.md) structure that contains a handle to the memory.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -prototype

```cpp
//Declaration

DXGKCB_MAPMDLTOIOMMU DxgkcbMapmdltoiommu;

// Definition

NTSTATUS DxgkcbMapmdltoiommu
(
	IN_CONST_HANDLE hAdapter
	INOUT_PDXGKARGCB_MAPMDLTOIOMMU pMapMdlToIoMmu
)
{...}

DXGKCB_MAPMDLTOIOMMU


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of [DXGKARGCB_MAPMDLTOIOMMU](ns-d3dkmddi-_dxgkargcb_mapmdltoiommu.md) and then calling DxgkCbMapMdlToIoMmu.

If the driver uses this callback, it is responsible for ensuring that the lifetime of the MDL exceeds the corresponding [DXGKCB_UNMAPMDLFROMIOMMU](nc-d3dkmddi-dxgkcb_unmapmdlfromiommu.md) call. Otherwise the DXGKCB_UNMAPMDLFROMIOMMU call has undefined behavior and may lead to compromised security of the pages from the MDL. The pages could get repurposed by Mm by the time they are unmapped.

## -see-also

