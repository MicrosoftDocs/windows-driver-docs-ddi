---
UID: NS:d3d12umddi.D3D12DDI_RANGED_BARRIER_0094
tech.root: display
title: D3D12DDI_RANGED_BARRIER_0094
ms.date: 10/17/2022
targetos: Windows
description: Learn more about the D3D12DDI_RANGED_BARRIER_0094 structure.
prerelease: false
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
req.typenames: D3D12DDI_RANGED_BARRIER_0094
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RANGED_BARRIER_0094
f1_keywords:
 - D3D12DDI_RANGED_BARRIER_0094
 - d3d12umddi/D3D12DDI_RANGED_BARRIER_0094
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_RANGED_BARRIER_0094
---

# D3D12DDI_RANGED_BARRIER_0094 structure (d3d12umddi.h)

## -description

The **D3D12DDI_RANGED_BARRIER_0094** structure describes a resource ranged barrier. This structure replaces the legacy [**D3D12DDI_RESOURCE_RANGED_BARRIER_0022**](ns-d3d12umddi-d3d12ddi_resource_ranged_barrier_0022.md) structure.

## -struct-fields

### -field Flags

A [**D3D12DDI_RANGED_BARRIER_FLAGS_0094**](ne-d3d12umddi-d3d12ddi_ranged_barrier_flags_0094.md) value that specifies flags for the ranged barrier.

### -field hResource

The handle of the resource using the barrier. A NULL value means that the entire GPU cache must be flushed or invalidated. A non-NULL value means that the flush or invalidate action affects a smaller subset of the cache that can contain data for that resource.

### -field Subresource

A [**D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088**](ns-d3d12umddi-d3d12ddi_barrier_subresource_range_0088.md) structure that specifies the range of subresources being barriered.

### -field Range

A [**D3D12DDI_RANGE**](ns-d3d12umddi-d3d12ddi_range.md) structure that describes a memory range.

## -remarks

Enhanced barriers fully deprecate the legacy ResourceBarrier DDIs. This includes the ranged barriers used internally by AtomicCopy commands.

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**D3D12DDI_RANGE**](ns-d3d12umddi-d3d12ddi_range.md)

[**D3D12DDIARG_BARRIER_0094**](ns-d3d12umddi-d3d12ddiarg_barrier_0094.md)

[**PFND3D12DDI_BARRIER_0094**](nc-d3d12umddi-pfnd3d12ddi_barrier_0094.md)
