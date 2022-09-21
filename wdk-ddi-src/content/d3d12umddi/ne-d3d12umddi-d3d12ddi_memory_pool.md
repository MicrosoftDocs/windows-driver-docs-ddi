---
UID: NE:d3d12umddi.D3D12DDI_MEMORY_POOL
tech.root: display
title: D3D12DDI_MEMORY_POOL
ms.date: 09/22/2022
targetos: Windows
description: Learn more about the D3D12DDI_MEMORY_POOL enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_MEMORY_POOL
f1_keywords:
 - D3D12DDI_MEMORY_POOL
 - d3d12umddi/D3D12DDI_MEMORY_POOL
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_MEMORY_POOL
---

## -description

A **D3D12DDI_MEMORY_POOL** value specifies the memory pool for the heap.

## -enum-fields

### -field D3D12DDI_MEMORY_POOL_L0:0

The memory pool is L0, which is the physical system memory pool. When the adapter is discrete/NUMA, this pool has greater bandwidth for the CPU and less bandwidth for the GPU. When the adapter is UMA, this pool is the only one that is valid.

### -field D3D12DDI_MEMORY_POOL_L1:1

The memory pool is L1, which is typically known as the physical (local) video memory pool. L1 is only available when the adapter is discrete/NUMA, and has greater bandwidth for the GPU and cannot even be accessed by the CPU. When the adapter is UMA, this pool is not available.

## -remarks

## -see-also

[**D3D12DDIARG_CREATEHEAP_0001**](ns-d3d12umddi-d3d12ddiarg_createheap_0001.md)
