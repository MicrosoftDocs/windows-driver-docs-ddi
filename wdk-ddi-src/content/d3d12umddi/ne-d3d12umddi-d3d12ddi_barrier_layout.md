---
UID: NE:d3d12umddi.D3D12DDI_BARRIER_LAYOUT
tech.root: display
title: D3D12DDI_BARRIER_LAYOUT
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDI_BARRIER_LAYOUT enumeration.
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
 - D3D12DDI_BARRIER_LAYOUT
f1_keywords:
 - D3D12DDI_BARRIER_LAYOUT
 - d3d12umddi/D3D12DDI_BARRIER_LAYOUT
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_BARRIER_LAYOUT
---

## -description

A **D3D12DDI_BARRIER_LAYOUT** value describes the possible layouts used by D3D12 subresources with respect to [texture barriers](ns-d3d12umddi-d3d12ddi_texture_barrier_0088.md). Layouts apply only to texture resources.

## -enum-fields

### -field D3D12DDI_BARRIER_LAYOUT_UNDEFINED:0xffffffff

Provides support for subresource layout changes where the previous layout is irrelevant or undefined. Typically, this is used for full-subresource or full-resource Clear, Discard, and Copy commands.

A layout transition with both **LayoutBefore** and **LayoutAfter** set to **D3D12_BARRIER_LAYOUT_UNDEFINED** indicates a memory-access-only barrier. Many read/write operations support **D3D12_BARRIER_LAYOUT_COMMON**. In particular, Copy commands can write to textures using either the **D3D12_BARRIER_LAYOUT_COMMON** or **D3D12_BARRIER_LAYOUT_COPY**. A memory-access-only barrier can be used to flush copy writes to a texture without changing the texture layout.

### -field D3D12DDI_BARRIER_LAYOUT_COMMON:0

This is the layout used by [**D3D12_RESOURCE_STATE_COMMON**](ne-d3d12umddi-d3d12ddi_resource_states.md). Subresources with this layout are readable in any queue type without requiring a layout change. They are also writeable as a copy destination in any queue type.

Swap chain presentation requires that the back buffer is using **D3D12_BARRIER_LAYOUT_COMMON**.

### -field D3D12DDI_BARRIER_LAYOUT_PRESENT:0

Alias for **D3D12_BARRIER_LAYOUT_COMMON**.

### -field D3D12DDI_BARRIER_LAYOUT_GENERIC_READ

Provides support for any read-only access (for example: SHADER_RESOURCE, COPY_SOURCE). This value should only be used for textures that require multiple, concurrent read accesses since this might not be as optimal as a more specific read layout.

### -field D3D12DDI_BARRIER_LAYOUT_RENDER_TARGET

Matches the layout used by [**D3D12_RESOURCE_STATE_RENDER_TARGET**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_UNORDERED_ACCESS

Matches the layout used by [**D3D12_RESOURCE_STATE_UNORDERED_ACCESS**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_DEPTH_STENCIL_WRITE

Matches the layout used by [**D3D12_RESOURCE_STATE_DEPTH_WRITE**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_DEPTH_STENCIL_READ

Matches the layout used by [**D3D12_RESOURCE_STATE_DEPTH_READ**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_SHADER_RESOURCE

Matches the layout used by [**D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE**](ne-d3d12umddi-d3d12ddi_resource_states.md) and **D3D12_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE**.

### -field D3D12DDI_BARRIER_LAYOUT_COPY_SOURCE

Matches the layout used by [**D3D12_RESOURCE_STATE_COPY_SOURCE**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_COPY_DEST

Matches the layout used by [**D3D12_RESOURCE_STATE_COPY_DEST**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_RESOLVE_SOURCE

Matches the layout used by [**D3D12DDI_RESOURCE_STATE_RESOLVE_SOURCE**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_RESOLVE_DEST

Matches the layout used by [**D3D12DDI_RESOURCE_STATE_RESOLVE_DEST**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_SHADING_RATE_SOURCE

Matches the layout used by [**D3D12DDI_RESOURCE_STATE_0062_SHADING_RATE_SOURCE**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_VIDEO_DECODE_READ

Matches the layout used by [**D3D12_RESOURCE_STATE_VIDEO_DECODE_READ**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_VIDEO_DECODE_WRITE

Matches the layout used by [**D3D12_RESOURCE_STATE_VIDEO_DECODE_WRITE**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_VIDEO_PROCESS_READ

Matches the layout used by [**D3D12_RESOURCE_STATE_VIDEO_PROCESS_READ**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_VIDEO_PROCESS_WRITE

Matches the layout used by [**D3D12_RESOURCE_STATE_VIDEO_PROCESS_WRITE**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_VIDEO_ENCODE_READ

Matches the layout used by [**D3D12_RESOURCE_STATE_VIDEO_ENCODE_READ**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_VIDEO_ENCODE_WRITE

Matches the layout used by [**D3D12_RESOURCE_STATE_VIDEO_ENCODE_WRITE**](ne-d3d12umddi-d3d12ddi_resource_states.md).

### -field D3D12DDI_BARRIER_LAYOUT_DIRECT_QUEUE_COMMON

Supports common (barrier free) usage on direct queues only. This value be more optimal than the more general **D3D12DDI_BARRIER_LAYOUT_COMMON**. Can only be used in barriers on direct queues.

Note that this cannot be used for Present. **D3D12_BARRIER_LAYOUT_COMMON** (also known as **D3D12_BARRIER_LAYOUT_PRESENT**) is still the required layout for Presentation.

### -field D3D12DDI_BARRIER_LAYOUT_DIRECT_QUEUE_GENERIC_READ

Same as **D3D12_BARRIER_LAYOUT_GENERIC_READ** except with optimizations specific for direct queues. Can only be used in barriers on direct queues.

In addition, **D3D12_BARRIER_LAYOUT_DIRECT_QUEUE_GENERIC_READ** includes support for read-only depth, shading-rate source, and resolve source accesses on direct queues.

### -field D3D12DDI_BARRIER_LAYOUT_DIRECT_QUEUE_UNORDERED_ACCESS

Same as **D3D12_BARRIER_LAYOUT_UNORDERED_ACCESS** except with optimizations specific for direct queues. Can only be used in barriers on direct queues.

### -field D3D12DDI_BARRIER_LAYOUT_DIRECT_QUEUE_SHADER_RESOURCE

Same as **D3D12_BARRIER_LAYOUT_SHADER_RESOURCE** except with optimizations specific for direct queues. Can only be used in barriers on direct queues.

### -field D3D12DDI_BARRIER_LAYOUT_DIRECT_QUEUE_COPY_SOURCE

Same as **D3D12_BARRIER_LAYOUT_COPY_SOURCE** except with optimizations specific for direct queues. Can only be used in barriers on direct queues.

### -field D3D12DDI_BARRIER_LAYOUT_DIRECT_QUEUE_COPY_DEST

Same as **D3D12_BARRIER_LAYOUT_COPY_DEST** except with optimizations specific for direct queues. Can only be used in barriers on direct queues. Can prevent costly and unnecessary decompression on some layout transitions on resources with next access in a Direct queue.

### -field D3D12DDI_BARRIER_LAYOUT_COMPUTE_QUEUE_COMMON

Supports common (barrier free) usage on compute queues only. May be more optimal than the more general **D3D12_BARRIER_LAYOUT_COMMON**. Can only be used in barriers on compute queues.

### -field D3D12DDI_BARRIER_LAYOUT_COMPUTE_QUEUE_GENERIC_READ

Same as **D3D12_BARRIER_LAYOUT_GENERIC_READ** except with optimizations specific for compute queues. Can only be used in barriers on compute queues.

### -field D3D12DDI_BARRIER_LAYOUT_COMPUTE_QUEUE_UNORDERED_ACCESS

Same as **D3D12_BARRIER_LAYOUT_UNORDERED_ACCESS** except with optimizations specific for compute queues. Can only be used in barriers on compute queues.

### -field D3D12DDI_BARRIER_LAYOUT_COMPUTE_QUEUE_SHADER_RESOURCE

Same as **D3D12_BARRIER_LAYOUT_SHADER_RESOURCE** except with optimizations specific for compute queues. Can only be used in barriers on compute queues.

### -field D3D12DDI_BARRIER_LAYOUT_COMPUTE_QUEUE_COPY_SOURCE

Same as **D3D12_BARRIER_LAYOUT_COPY_SOURCE** except with optimizations specific for compute queues. Can only be used in barriers on compute queues.

### -field D3D12DDI_BARRIER_LAYOUT_COMPUTE_QUEUE_COPY_DEST

Same as **D3D12_BARRIER_LAYOUT_COPY_DEST** except with optimizations specific for compute queues. Can only be used in barriers on compute queues.

### -field D3D12DDI_BARRIER_LAYOUT_VIDEO_QUEUE_COMMON

Supports common (barrier free) usage on video queues only. May be more optimal than the more general **D3D12_BARRIER_LAYOUT_COMMON**. Can only be used in barriers on video queues.

### -field D3D12DDI_BARRIER_LAYOUT_LEGACY_COPY_SOURCE:0x80000000

Supports an internally-translated legacy resource state. No enhanced barrier APIs map to this value.

### -field D3D12DDI_BARRIER_LAYOUT_LEGACY_COPY_DEST

Supports an internally-translated legacy resource state. No enhanced barrier APIs map to this value.

### -field D3D12DDI_BARRIER_LAYOUT_LEGACY_SHADER_RESOURCE

Supports an internally-translated legacy resource state. No enhanced barrier APIs map to this value.

### -field D3D12DDI_BARRIER_LAYOUT_LEGACY_PIXEL_SHADER_RESOURCE

Supports an internally-translated legacy resource state. No enhanced barrier APIs map to this value.

## -remarks

Buffer resources have only a linear layout, regardless of access type.

Resource layouts must be compatible with the type of queue performing the layout transition.

## -see-also

[**D3D12DDI_TEXTURE_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_texture_barrier_0088.md)
