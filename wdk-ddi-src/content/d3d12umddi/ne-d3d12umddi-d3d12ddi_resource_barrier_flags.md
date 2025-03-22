---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_BARRIER_FLAGS
title: D3D12DDI_RESOURCE_BARRIER_FLAGS (d3d12umddi.h)
description: Contains resource barrier flags.
old-location: display\d3d12ddi_resource_barrier_flags.htm
ms.date: 10/17/2022
keywords: ["D3D12DDI_RESOURCE_BARRIER_FLAGS enumeration"]
ms.keywords: D3D12DDI_RESOURCE_BARRIER_FLAGS, D3D12DDI_RESOURCE_BARRIER_FLAGS enumeration [Display Devices], D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING, D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY, D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY, D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY, D3D12DDI_RESOURCE_BARRIER_FLAG_NONE, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAGS, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_NONE, display.d3d12ddi_resource_barrier_flags
req.header: d3d12umddi.h
req.construct-type: enumeration
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_RESOURCE_BARRIER_FLAGS
f1_keywords:
 - D3D12DDI_RESOURCE_BARRIER_FLAGS
 - d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_RESOURCE_BARRIER_FLAGS
---

# D3D12DDI_RESOURCE_BARRIER_FLAGS enumeration (d3d12umddi.h)



## -description

**D3D12DDI_RESOURCE_BARRIER_FLAGS** contains legacy resource barrier flags.

## -enum-fields

### -field D3D12DDI_RESOURCE_BARRIER_FLAG_NONE:0x0

No flag value.

### -field D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY:0x1

Indicates an acquire. This starts a barrier transition in a new state, putting a resource in a temporary no-access condition. This flag is relevant only for ranged barriers.

### -field D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY:0x2

Indicates a release. This barrier completes a transition, setting a new state and restoring active access to a resource. This flag is relevant only for ranged barriers.

### -field D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY:0x4

Indicates that ranged barriers are associated with a parameter of an atomic copy operation.

### -field D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING:0x8

Indicates that an aliasing barrier has been converted to a ranged barrier.

## -remarks

The absence of both **D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY** and **D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY** denotes both an acquire and release.

During an acquire, GPU caches may need to be explicitly invalidated. During a release, GPU caches may need to be explicitly flushed.

## -see-also

[**D3D12DDI_RANGED_BARRIER_FLAGS_0094**](ne-d3d12umddi-d3d12ddi_ranged_barrier_flags_0094.md)
