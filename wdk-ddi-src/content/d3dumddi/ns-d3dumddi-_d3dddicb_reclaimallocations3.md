---
UID: NS:d3dumddi._D3DDDICB_RECLAIMALLOCATIONS3
title: _D3DDDICB_RECLAIMALLOCATIONS3 (d3dumddi.h)
description: D3DDDICB_RECLAIMALLOCATIONS3 is used with pfnReclaimAllocations3Cb to describe video memory resources, previously offered for reuse by the driver, that are to be reclaimed.
ms.assetid: 11306f6b-dfb5-4357-9bf2-14c4c4034594
ms.date: 10/19/2018
keywords: ["_D3DDDICB_RECLAIMALLOCATIONS3 structure"]
f1_keywords:
 - "d3dumddi/_D3DDDICB_RECLAIMALLOCATIONS3"
ms.keywords: _D3DDDICB_RECLAIMALLOCATIONS3, D3DDDICB_RECLAIMALLOCATIONS3, 
req.header: d3dumddi.h
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
req.typenames: D3DDDICB_RECLAIMALLOCATIONS3
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dumddi.h
api_name: 
- _D3DDDICB_RECLAIMALLOCATIONS3
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DDDICB_RECLAIMALLOCATIONS3 structure

## -description

D3DDDICB_RECLAIMALLOCATIONS3 is used with pfnReclaimAllocations3Cb to describe video memory resources, previously offered for reuse by the driver, that are to be reclaimed.

## -struct-fields

### -field PagingQueue

The paging queue, supplied by the user-mode driver, to page in the allocation list.

### -field NumAllocations

The number of allocations in **HandleList**.

### -field pResources

An array of Direct3D runtime resource handles.

### -field HandleList

An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations.

### -field pResults

Required array of values specifying whether the surface is valid, discarded, or list commitment.

### -field PagingFenceValue
 
The paging fence to synchronize against before submitting work to the GPU, which references any of the resources or allocations in the provided arrays.

## -remarks

## -see-also
