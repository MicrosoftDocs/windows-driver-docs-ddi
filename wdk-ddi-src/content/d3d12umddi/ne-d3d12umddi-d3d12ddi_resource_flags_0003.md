---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_FLAGS_0003
tech.root: display
title: D3D12DDI_RESOURCE_FLAGS_0003 (d3d12umddi.h)
description: Specifies resource flag values.
old-location: display\d3d12ddi_resource_flags_0003.htm
ms.date: 09/22/2022
keywords: ["D3D12DDI_RESOURCE_FLAGS_0003 enumeration"]
ms.keywords: D3D12DDI_RESOURCE_FLAGS_0003, D3D12DDI_RESOURCE_FLAGS_0003 enumeration [Display Devices], D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER, D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL, D3D12DDI_RESOURCE_FLAG_0003_NONE, D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET, D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE, D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS, D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION, D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY, D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS, d3d12umddi/D3D12DDI_RESOURCE_FLAGS_0003, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_NONE, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS, display.d3d12ddi_resource_flags_0003
req.header: d3d12umddi.h
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
req.typenames: D3D12DDI_RESOURCE_FLAGS_0003
f1_keywords:
 - D3D12DDI_RESOURCE_FLAGS_0003
 - d3d12umddi/D3D12DDI_RESOURCE_FLAGS_0003
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_RESOURCE_FLAGS_0003
---

# D3D12DDI_RESOURCE_FLAGS_0003 enumeration

## -description

The **D3D12DDI_RESOURCE_FLAGS_0003** enumeration specifies resource flag values.

## -enum-fields

### -field D3D12DDI_RESOURCE_FLAG_0003_NONE:0x0

No flags are specified.

### -field D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET:0x1

When set, allows a render target view to be created for the resource.

### -field D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL:0x2

When set, allows a depth stencil view to be created for the resource.

### -field D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER:0x4

When set, allows the resource to be used for cross-adapter data.

### -field D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS:0x8

When set, allows a resource to be accessed simultaneously by multiple different queues, devices, or processes.

### -field D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE:0x10

When set, allows a shader resource view to be created for the resource.

### -field D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY:0x20

When set, this resource can only be used as a decode reference frame. It can only be written to or read by the video decode operation.

### -field D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION:0x40

When set, the resource can be used to support content protection.

### -field D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS:0x80

When set, allows unordered access. This value is available as a resource flag for the fallback plans.

### -field D3D12DDI_RESOURCE_FLAG_0041_ONLY_NON_RT_DS_TEXTURE_PLACEMENT:0x100

Not currently used.

### -field D3D12DDI_RESOURCE_FLAG_0041_ONLY_RT_DS_TEXTURE_PLACEMENT:0x200

Not currently used.

### -field D3D12DDI_RESOURCE_FLAG_0041_4MB_ALIGNED:0x400

Not currently used.

### -field D3D12DDI_RESOURCE_FLAG_0073_SAMPLER_FEEDBACK:0x800

When set, allows the resource to be used for sampler feedback.

### -field D3D12DDI_RESOURCE_FLAG_0080_VIDEO_ENCODE_REFERENCE_ONLY:0x1000

When set, this resource can only be used as a video encode reference frame. It can only be written to or read by the video encode operation.

### -field D3D12DDI_RESOURCE_FLAG_0088_RAYTRACING_ACCELERATION_STRUCTURE:0x2000

When set, the resource can be used as an acceleration structure for ray tracing.

## -see-also

[**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md)
