---
UID: NS:d3d12umddi.D3D12DDI_GLOBAL_BARRIER_0088
tech.root: display
title: D3D12DDI_GLOBAL_BARRIER_0088
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDI_GLOBAL_BARRIER_0088 structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_GLOBAL_BARRIER_0088
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_GLOBAL_BARRIER_0088
f1_keywords:
 - D3D12DDI_GLOBAL_BARRIER_0088
 - d3d12umddi/D3D12DDI_GLOBAL_BARRIER_0088
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_GLOBAL_BARRIER_0088
---

## -description

The **D3D12DDI_GLOBAL_BARRIER_0088** structure describes a resource memory access barrier. This barrier is used by global, texture, and buffer barriers to indicate when resource memory must be made visible for a specific access type.

## -struct-fields

### -field SyncBefore

A [**D3D12DDI_BARRIER_SYNC**](ne-d3d12umddi-d3d12ddi_barrier_sync.md) value that specifies the synchronization scope of all preceding GPU work that must be completed before executing the barrier.

### -field SyncAfter

A [**D3D12DDI_BARRIER_SYNC**](ne-d3d12umddi-d3d12ddi_barrier_sync.md) value that specifies the synchronization scope of all subsequent GPU work that must wait until the barrier execution is finished.

### -field AccessBefore

A [**D3D12DDI_BARRIER_ACCESS**](ne-d3d12umddi-d3d12ddi_barrier_access.md) value that specifies the write accesses that must be flushed and finished before the barrier is executed.

### -field AccessAfter

A [**D3D12DDI_BARRIER_ACCESS**](ne-d3d12umddi-d3d12ddi_barrier_access.md) value that specifies the accesses that must be available for data written via **AccessBefore** after the barrier is executed.

## -remarks

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**D3D12DDI_BARRIER_ACCESS**](ne-d3d12umddi-d3d12ddi_barrier_access.md)

[**D3D12DDI_BARRIER_SYNC**](ne-d3d12umddi-d3d12ddi_barrier_sync.md)

[**D3D12DDIARG_BARRIER_0088**](ns-d3d12umddi-d3d12ddiarg_barrier_0088.md)

[**PFND3D12DDI_BARRIER_0088**](nc-d3d12umddi-pfnd3d12ddi_barrier_0088.md)
