---
UID: NS:d3d12umddi.D3D12DDIARG_MAKERESIDENT_0001
title: D3D12DDIARG_MAKERESIDENT_0001 (d3d12umddi.h)
description: Arguments used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
ms.assetid: 93ecb8e8-62e8-48c5-ad7c-3f1f06a69424
ms.date: 10/19/2018
keywords: ["D3D12DDIARG_MAKERESIDENT_0001 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_MAKERESIDENT_0001"
ms.keywords: D3D12DDIARG_MAKERESIDENT_0001, D3D12DDIARG_MAKERESIDENT_0001, 
req.header: d3d12umddi.h
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
req.typenames: D3D12DDIARG_MAKERESIDENT_0001
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDIARG_MAKERESIDENT_0001
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: RS5, 19H1
tech.root: display
---

# D3D12DDIARG_MAKERESIDENT_0001 structure

## -description

Arguments used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.

## -struct-fields

### -field NumAdapters

The number of adapters.

### -field pRTPagingQueue

Paging queue on the device that created the input allocations. This queue will be used for residency operations.

### -field NumObjects

The number of objects.

### -field pObjects

An array of adapters to make resident.

### -field Flags

Specifies memory residency behavior.

### -field Flags.CantTrimFurther
 
### -field Flags.Value

### -field pPagingFenceValue

Pointer to the paging queue fence value to wait on.

### -field WaitMask
 
The wait mask.

## -remarks

## -see-also
