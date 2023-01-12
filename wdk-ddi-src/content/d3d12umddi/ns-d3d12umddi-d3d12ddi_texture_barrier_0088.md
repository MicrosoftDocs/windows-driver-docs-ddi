---
UID: NS:d3d12umddi.D3D12DDI_TEXTURE_BARRIER_0088
tech.root: display
title: D3D12DDI_TEXTURE_BARRIER_0088
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDI_TEXTURE_BARRIER_0088 structure.
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
req.typenames: D3D12DDI_TEXTURE_BARRIER_0088
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_TEXTURE_BARRIER_0088
f1_keywords:
 - D3D12DDI_TEXTURE_BARRIER_0088
 - d3d12umddi/D3D12DDI_TEXTURE_BARRIER_0088
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_TEXTURE_BARRIER_0088
---

## -description

A **D3D12DDI_TEXTURE_BARRIER_0088** structure describes access transitions for textures.

## -struct-fields

### -field SyncBefore

A [**D3D12DDI_BARRIER_SYNC**](ne-d3d12umddi-d3d12ddi_barrier_sync.md) value that specifies the synchronization scope of all preceding GPU work that must be completed before executing the barrier.

### -field SyncAfter

A [**D3D12DDI_BARRIER_SYNC**](ne-d3d12umddi-d3d12ddi_barrier_sync.md) value that specifies the synchronization scope of all subsequent GPU work that must wait until the barrier execution is finished.

### -field AccessBefore

A [**D3D12DDI_BARRIER_ACCESS**](ne-d3d12umddi-d3d12ddi_barrier_access.md) value that specifies the access state of the texture preceding the barrier execution.

### -field AccessAfter

A [**D3D12DDI_BARRIER_ACCESS**](ne-d3d12umddi-d3d12ddi_barrier_access.md) value that specifies the access state of the texture upon completion of barrier execution.

### -field LayoutBefore

A [**D3D12DDI_BARRIER_LAYOUT**](ne-d3d12umddi-d3d12ddi_barrier_layout.md) value that specifies the layout of the texture preceding the barrier execution.

### -field LayoutAfter

A [**D3D12DDI_BARRIER_LAYOUT**](ne-d3d12umddi-d3d12ddi_barrier_layout.md) value that specifies the layout of the texture upon completion of barrier execution.

### -field hResource

The handle of the texture resource using the barrier.

### -field Subresources

A [**D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088**](ns-d3d12umddi-d3d12ddi_barrier_subresource_range_0088.md) structure that specifies the range of texture subresources being barriered.

### -field Flags

A [**D3D12DDI_TEXTURE_BARRIER_FLAGS_0088**](ne-d3d12umddi-d3d12ddi_texture_barrier_flags_0088.md) value that specifies optional flags.

## -remarks

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

### Synchronization

Graphics processors are designed to execute as much work in parallel as possible. Any GPU work that depends on previous GPU work must be synchronized before accessing dependent data. The **SyncBefore** and **SyncAfter** values are logical bitfield masks that identify any work to synchronize.

A Barrier must wait for all preceding command **SyncBefore** scopes to complete before executing the barrier. Similarly, a Barrier must block all subsequent **SyncAfter** scopes until the barrier completes.

### Layout transitions

Texture subresources can use different layouts for various access methods. For example, textures are often compressed when used as a render target or depth stencil and are often uncompressed for shader read or copy commands. Texture Barriers use **LayoutBefore** and **LayoutAfter** to describe layout transitions.

Layout transitions are only needed for textures, therefore they are expressed only in this data structure.

Both **LayoutBefore** and **LayoutAfter** must be compatible with the type of queue performing the barrier. For example, a compute queue cannot transition a subresource into or out of **D3D12_BARRIER_LAYOUT_RENDER_TARGET**.

To provide well-defined barrier ordering, the layout of a subresource after completing a sequence of barriers is the final **LayoutAfter** in the sequence.

## -see-also

[**D3D12DDI_BARRIER_ACCESS**](ne-d3d12umddi-d3d12ddi_barrier_access.md)

[**D3D12DDI_BARRIER_LAYOUT**](ne-d3d12umddi-d3d12ddi_barrier_layout.md)

[**D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088**](ns-d3d12umddi-d3d12ddi_barrier_subresource_range_0088.md)

[**D3D12DDI_BARRIER_SYNC**](ne-d3d12umddi-d3d12ddi_barrier_sync.md)

[**D3D12DDI_TEXTURE_BARRIER_FLAGS_0088**](ne-d3d12umddi-d3d12ddi_texture_barrier_flags_0088.md)

[**D3D12DDIARG_BARRIER_0088**](ns-d3d12umddi-d3d12ddiarg_barrier_0088.md)

[**PFND3D12DDI_BARRIER_0088**](nc-d3d12umddi-pfnd3d12ddi_barrier_0088.md)
