---
UID: NE:d3d12umddi.D3D12DDI_BARRIER_ACCESS
tech.root: display
title: D3D12DDI_BARRIER_ACCESS
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDI_BARRIER_ACCESS enumeration.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
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
 - D3D12DDI_BARRIER_ACCESS
f1_keywords:
 - D3D12DDI_BARRIER_ACCESS
 - d3d12umddi/D3D12DDI_BARRIER_ACCESS
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_BARRIER_ACCESS
---

## -description

A **D3D12DDI_BARRIER_ACCESS** value is a bit-wise OR of the following fields that specify resource access with respect to a barrier.

## -enum-fields

### -field D3D12DDI_BARRIER_ACCESS_COMMON:0x0

The default initial access for all resources in a given ExecuteCommandLists scope. Supports any type of access compatible with current layout and resource properties, including no more than one write access. For buffers and textures using [**D3D12DDI_BARRIER_LAYOUT_COMMON**](ne-d3d12umddi-d3d12ddi_barrier_layout.md), **D3D12DDI_BARRIER_ACCESS_COMMON** supports concurrent read and write accesses.

When used as **AccessAfter**, **D3D12DDI_BARRIER_ACCESS_COMMON** can be used to return a resource back to common accessibility. Note that this might force unnecessary cache flushes if used incorrectly. When possible, **AccessAfter** should be limited to explicit access bits.

Avoid using D3D12DDI_BARRIER_ACCESS_COMMON as a barrier **AccessBefore** value. Any read-after-write or write-after-write hazards are best handled using explicit **AccessBefore** bits.

### -field D3D12DDI_BARRIER_ACCESS_VERTEX_BUFFER:0x1

A buffer resource is accessible as a vertex buffer in the current execution queue.

### -field D3D12DDI_BARRIER_ACCESS_CONSTANT_BUFFER:0x2

A buffer resource is accessible as a constant buffer in the current execution queue.

### -field D3D12DDI_BARRIER_ACCESS_INDEX_BUFFER:0x4

A buffer resource is accessible as an index buffer in the current execution queue.

### -field D3D12DDI_BARRIER_ACCESS_RENDER_TARGET:0x8

A resource is accessible as a render target.

### -field D3D12DDI_BARRIER_ACCESS_UNORDERED_ACCESS:0x10

A resource is accessible as an unordered access resource.

### -field D3D12DDI_BARRIER_ACCESS_DEPTH_STENCIL_WRITE:0x20

A resource is accessible as a writeable depth/stencil resource.

### -field D3D12DDI_BARRIER_ACCESS_DEPTH_STENCIL_READ:0x40

A resource is accessible as a read-only depth/stencil resource.

### -field D3D12DDI_BARRIER_ACCESS_SHADER_RESOURCE:0x80

A resource is accessible as a shader resource.

### -field D3D12DDI_BARRIER_ACCESS_STREAM_OUTPUT:0x100

A buffer is accessible as a stream output target.

### -field D3D12DDI_BARRIER_ACCESS_INDIRECT_ARGUMENT:0x200

A buffer is accessible as an indirect argument buffer.

### -field D3D12DDI_BARRIER_ACCESS_PREDICATION:0x200

A buffer is accessible as a predication buffer. Aliased with **D3D12DDI_BARRIER_ACCESS_INDIRECT_ARGUMENT**.

### -field D3D12DDI_BARRIER_ACCESS_COPY_DEST:0x400

A resource is accessible as a copy destination.

### -field D3D12DDI_BARRIER_ACCESS_COPY_SOURCE:0x800

A resource is accessible as a copy source.

### -field D3D12DDI_BARRIER_ACCESS_RESOLVE_DEST:0x1000

A resource is accessible as a resolve destination.

### -field D3D12DDI_BARRIER_ACCESS_RESOLVE_SOURCE:0x2000

A resource is accessible as a resolve source.

### -field D3D12DDI_BARRIER_ACCESS_RAYTRACING_ACCELERATION_STRUCTURE_READ:0x4000

A resource is accessible for read as a ray tracing acceleration structure. The resource must have been created using an initial state of [**D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_ACCESS_RAYTRACING_ACCELERATION_STRUCTURE_WRITE:0x8000

A resource is accessible for write as a ray tracing acceleration structure. The resource must have been created using an initial state of [**D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_ACCESS_SHADING_RATE_SOURCE:0x10000

A resource is accessible as a shading rate source.

### -field D3D12DDI_BARRIER_ACCESS_VIDEO_DECODE_READ:0x20000

A resource is accessible for read-only access in a video decode queue.

### -field D3D12DDI_BARRIER_ACCESS_VIDEO_DECODE_WRITE:0x40000

A resource is accessible for write access in a video decode queue.

### -field D3D12DDI_BARRIER_ACCESS_VIDEO_PROCESS_READ:0x80000

A resource is accessible for read-only access in a video process queue.

### -field D3D12DDI_BARRIER_ACCESS_VIDEO_PROCESS_WRITE:0x100000

A resource is accessible for write access in a video process queue.

### -field D3D12DDI_BARRIER_ACCESS_VIDEO_ENCODE_READ:0x200000

A resource is accessible for read-only access in a video encode queue.

### -field D3D12DDI_BARRIER_ACCESS_VIDEO_ENCODE_WRITE:0x400000

A resource is accessible for write access in a video encode queue.

### -field D3D12DDI_BARRIER_ACCESS_NO_ACCESS:0x80000000

A resource is inaccessible for read or write. Once a subresource access has been transitioned to **D3D12DDI_BARRIER_ACCESS_NO_ACCESS**, it must be be reactivated by a barrier with **AccessBefore** set to **D3D12DDI_BARRIER_ACCESS_NO_ACCESS** before using in the same ExecuteCommandLists scope.

**D3D12DDI_BARRIER_ACCESS_NO_ACCESS** can only be used in conjunction with **D3D12DDI_BARRIER_SYNC_NONE** or **D3D12DDI_BARRIER_SYNC_SPLIT**.

**D3D12DDI_BARRIER_ACCESS_NO_ACCESS** cannot be set with other access bits. **D3D12DDI_BARRIER_ACCESS_NO_ACCESS** indicates a resource is not expected to be accessed until some subsequent barrier or the next ECL scope.

This value is useful in aliasing barriers when a subresource is not needed for a sufficiently long time that it makes sense to purge the subresource from any read cache.

It is also useful for initiating a layout transition as the final act on a resource before the end of an ExecuteCommandLists scope. If **SyncAfter** is **D3D12DDI_BARRIER_SYNC_NONE**, then **AccessAfter** MUST be **D3D12DDI_BARRIER_ACCESS_NO_ACCESS**.

## -remarks

## -see-also

[**D3D12DDI_BARRIER_SYNC**](ne-d3d12umddi-d3d12ddi_barrier_sync.md)

[**D3D12DDI_BUFFER_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_buffer_barrier_0088.md)

[**D3D12DDI_GLOBAL_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_global_barrier_0088.md)

[**D3D12DDI_RANGED_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_ranged_barrier_0088.md)

[**D3D12DDI_TEXTURE_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_texture_barrier_0088.md)
