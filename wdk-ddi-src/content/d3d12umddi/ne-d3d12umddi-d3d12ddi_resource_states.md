---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_STATES
title: D3D12DDI_RESOURCE_STATES (d3d12umddi.h)
description: Contains resource states.
old-location: display\d3d12ddi_resource_states.htm
ms.date: 05/24/2022
keywords: ["D3D12DDI_RESOURCE_STATES enumeration"]
ms.keywords: D3D12DDI_RESOURCE_STATES, D3D12DDI_RESOURCE_STATES enumeration [Display Devices], D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_READ, D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_WRITE, D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_READ, D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_WRITE, D3D12DDI_RESOURCE_STATE_COMMON, D3D12DDI_RESOURCE_STATE_COPY_DEST, D3D12DDI_RESOURCE_STATE_COPY_SOURCE, D3D12DDI_RESOURCE_STATE_DEPTH_READ, D3D12DDI_RESOURCE_STATE_DEPTH_WRITE, D3D12DDI_RESOURCE_STATE_INDEX_BUFFER, D3D12DDI_RESOURCE_STATE_INDIRECT_ARGUMENT, D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE, D3D12DDI_RESOURCE_STATE_PIXEL_SHADER_RESOURCE, D3D12DDI_RESOURCE_STATE_RENDER_TARGET, D3D12DDI_RESOURCE_STATE_RESOLVE_DEST, D3D12DDI_RESOURCE_STATE_RESOLVE_SOURCE, D3D12DDI_RESOURCE_STATE_STREAM_OUT, D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS, D3D12DDI_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER, d3d12umddi/D3D12DDI_RESOURCE_STATES, d3d12umddi/D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_READ, d3d12umddi/D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_WRITE, d3d12umddi/D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_READ, d3d12umddi/D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_WRITE, d3d12umddi/D3D12DDI_RESOURCE_STATE_COMMON, d3d12umddi/D3D12DDI_RESOURCE_STATE_COPY_DEST, d3d12umddi/D3D12DDI_RESOURCE_STATE_COPY_SOURCE, d3d12umddi/D3D12DDI_RESOURCE_STATE_DEPTH_READ, d3d12umddi/D3D12DDI_RESOURCE_STATE_DEPTH_WRITE, d3d12umddi/D3D12DDI_RESOURCE_STATE_INDEX_BUFFER, d3d12umddi/D3D12DDI_RESOURCE_STATE_INDIRECT_ARGUMENT, d3d12umddi/D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE, d3d12umddi/D3D12DDI_RESOURCE_STATE_PIXEL_SHADER_RESOURCE, d3d12umddi/D3D12DDI_RESOURCE_STATE_RENDER_TARGET, d3d12umddi/D3D12DDI_RESOURCE_STATE_RESOLVE_DEST, d3d12umddi/D3D12DDI_RESOURCE_STATE_RESOLVE_SOURCE, d3d12umddi/D3D12DDI_RESOURCE_STATE_STREAM_OUT, d3d12umddi/D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS, d3d12umddi/D3D12DDI_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER, display.d3d12ddi_resource_states
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: Direct3D 12.0
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
req.typenames: D3D12DDI_RESOURCE_STATES
ms.custom: 19H1
f1_keywords:
 - D3D12DDI_RESOURCE_STATES
 - d3d12umddi/D3D12DDI_RESOURCE_STATES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_RESOURCE_STATES
dev_langs:
 - c++
---

# D3D12DDI_RESOURCE_STATES enumeration

## -description

Contains resource states. Resource barriers allow transitioning between hardware specific states for a corresponding operation and to synchronize read after write. Resource barriers are an existing concept in D3D12 that is extended to support video decode and video process by adding these usage flags.

## -enum-fields

### -field D3D12DDI_RESOURCE_STATE_COMMON:0x00000000

Common.

### -field D3D12DDI_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER:0x00000001

Vertex and constant buffer.

### -field D3D12DDI_RESOURCE_STATE_INDEX_BUFFER:0x00000002

Index buffer.

### -field D3D12DDI_RESOURCE_STATE_RENDER_TARGET:0x00000004

Render target.

### -field D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS:0x00000008

Unordered access.

### -field D3D12DDI_RESOURCE_STATE_DEPTH_WRITE:0x00000010

Depth write.

### -field D3D12DDI_RESOURCE_STATE_DEPTH_READ:0x00000020

Depth read.

### -field D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE:0x00000040

Non-pixel shader resource.

### -field D3D12DDI_RESOURCE_STATE_PIXEL_SHADER_RESOURCE:0x00000080

Pixel shader resource.

### -field D3D12DDI_RESOURCE_STATE_STREAM_OUT:0x00000100

Stream out.

### -field D3D12DDI_RESOURCE_STATE_INDIRECT_ARGUMENT:0x00000200

Indirect argument.

### -field D3D12DDI_RESOURCE_STATE_COPY_DEST:0x00000400

Copy destination.

### -field D3D12DDI_RESOURCE_STATE_COPY_SOURCE:0x00000800

Copy source.

### -field D3D12DDI_RESOURCE_STATE_RESOLVE_DEST:0x00001000

Resolve destination.

### -field D3D12DDI_RESOURCE_STATE_RESOLVE_SOURCE:0x00002000

Resolve source.

### -field D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_READ:0x00010000

Video decode read. The read state is used for reading references during decode and also used for inputs to process frame. This state is only valid in the decode and process command list.

### -field D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_WRITE:0x00020000

Video decode write. The write state is used for the decode target, or destination surface of the process frame. The write state is also used when decode conversion is enabled for the non-converted reference. This state is only valid in the decode and process command list.

### -field D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_READ:0x00040000

Video process read.

### -field D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_WRITE:0x00080000

Video process write.

### -field D3D12DDI_RESOURCE_STATE_0060_VIDEO_ENCODE_READ:0x00200000

Video encode read resource state.

### -field D3D12DDI_RESOURCE_STATE_0060_VIDEO_ENCODE_WRITE:0x00800000

Video encode write resource state.

### -field D3D12DDI_RESOURCE_STATE_0062_SHADING_RATE_SOURCE:0x01000000

Shading rate source resource state.

Available starting in WDDM 2.6.

### -field D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE:0x400000

Ray tracing acceleration structure resource state.

## -remarks

Resource barriers allow transitioning between hardware specific states for a corresponding operation and to synchronize read after write.

Resource barriers are an existing concept in D3D12 that is extended to support video decode by adding new usage flags.
The write state is used for the decode target. The write state is also used when decode conversion is enabled for the non-converted reference.
