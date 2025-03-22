---
UID: NE:d3d12umddi.D3D12DDI_RANGED_BARRIER_FLAGS_0094
tech.root: display
title: D3D12DDI_RANGED_BARRIER_FLAGS_0094
ms.date: 10/17/2022
targetos: Windows
description: Learn more about the D3D12DDI_RANGED_BARRIER_FLAGS_0094 enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
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
 - D3D12DDI_RANGED_BARRIER_FLAGS_0094
f1_keywords:
 - D3D12DDI_RANGED_BARRIER_FLAGS_0094
 - d3d12umddi/D3D12DDI_RANGED_BARRIER_FLAGS_0094
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_RANGED_BARRIER_FLAGS_0094
---

# D3D12DDI_RANGED_BARRIER_FLAGS_0094 enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_RANGED_BARRIER_FLAGS_0094** enumeration specifies flags for ranged barriers.

## -enum-fields

### -field D3D12DDI_RANGED_BARRIER_FLAG_NONE_0094

No flags are specified.

### -field D3D12DDI_RANGED_BARRIER_FLAG_ATOMIC_COPY_0094

The barrier is associated with a parameter of an atomic copy operation.

### -field D3D12DDI_RANGED_BARRIER_FLAG_ACQUIRE_0094

Acquire a buffer range for AtomicCopy operations.

### -field D3D12DDI_RANGED_BARRIER_FLAG_RELEASE_0094

Release a buffer range from AtomicCopy operations.

## -remarks

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**D3D12DDI_RANGED_BARRIER_0094**]*(ns-d3d12umddi-d3d12ddi_ranged_barrier_0094.md)
