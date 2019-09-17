---
UID: NE:d3d12umddi.D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE
title: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE (d3d12umddi.h)
description: Type of copy operation to perform.
ms.assetid: 382dddf5-3cbe-4c32-b1c2-778e0b1d855e
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE, D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE"
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE enumeration

## -description

Type of copy operation to perform.

## -enum-fields

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE_CLONE

Copy an acceleration structure while fixing up any self-referential pointers that may be present, so that the destination is a self-contained match for the source. Any external pointers to other acceleration structures remain unchanged from source to destination in the copy. The size of the destination is identical to the size of the source.

The source and destination memory must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE_COMPACT

Similar to the clone mode, produces a functionally equivalent acceleration structure to source in the destination. Compact mode also fits the destination into a potentially smaller memory footprint. The size required for the destination can be retrieved beforehand from [EmitRaytracingAccelerationStructurePostBuildInfo](nc-d3d12umddi-pfnd3d12ddi_emit_raytracing_acceleration_structure_postbuild_info_0054.md).  

This mode is only valid if the source acceleration structure was originally built with the D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_ALLOW_COMPACTION flag of the [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS](ne-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_build_flags.md) enumeration, otherwise results are undefined.

The source and destination memory must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE_VISUALIZATION_DECODE_FOR_TOOLS

Destination takes after the layout described in [D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054](ns-d3d12umddi-d3d12ddi_build_raytracing_acceleration_structure_tools_visualization_header_0054.md). The size required for the destination can be retrieved beforehand from [EmitRaytracingAccelerationStructurePostBuildInfo](nc-d3d12umddi-pfnd3d12ddi_emit_raytracing_acceleration_structure_postbuild_info_0054.md).

This mode is intended for tools such as [PIX on Windows](https://devblogs.microsoft.com/pix/introducing-pix-on-windows-beta/) only, though nothing stops any app from using it. The output is essentially the inverse of an acceleration structure build.  

For top-level acceleration structures, the output includes a set of instance descriptions that are identical to the data used in the original build and in the same order.  

For bottom-level acceleration structures, the output includes a set of geometry descriptions roughly matching the data used in the original build. The output is only a rough match for the original in part because of the tolerances allowed in the specification for acceleration structures, and in part because reporting exactly the same structure as is conceptually encoded may not be simple.  

AABBs (axis-aligned bounding box) returned for procedural primitives, for instance, could be more conservative (e.g. larger) in volume and even different in number than what is actually in the acceleration structure representation, because it may not be clean to expose the exact representation.  

Geometries, each with its own geometry description, must appear in the same order as in the original build, as shader table indexing calculations depends on this.

This overall structure with is sufficient for tools such as PIX on Windows to be able to give the application some visual sense of the acceleration structure the driver made out of the app’s input. Visualization can help reveal driver bugs in acceleration structures if what is shown grossly mismatches the data the application used to create the acceleration structure, beyond allowed tolerances.

The source memory must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE. The destination memory must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS.

This mode is only permitted when developer mode is enabled on the OS.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE_SERIALIZE

Destination takes the layout and size described in [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_postbuild_info_serialization_desc_0054.md), via [EmitRaytracingAccelerationStructurePostBuildInfo](nc-d3d12umddi-pfnd3d12ddi_emit_raytracing_acceleration_structure_postbuild_info_0054.md).  

This serializes an acceleration structure so that tools such as PIX on Windows can store to a file for later playback, via deserialization.  While intended for tools such as PIX for Windows, nothing stops any app from using this.

The source memory must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE. The destination memory must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS.

When serializing a top-level acceleration structure the bottom-level acceleration structures it refers to do not have to still be present or intact in memory.  Likewise, bottom-level acceleration structures can be serialized independent of whether any top-level acceleration structures are pointing to them. Said another way, the order of serialization of acceleration structures doesn’t matter.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE_DESERIALIZE

Source must be a serialized acceleration structure, with any pointers, directly after the header, fixed to point to their new locations, as discussed in the [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_postbuild_info_serialization_desc_0054.md) structure.  

Destination gets an acceleration structure that is functionally equivalent to the acceleration structure that was originally serialized. It does not matter what order top-level and bottom-level acceleration structures, that the top-level refers to, are deserialized, as long as by the time a top-level acceleration structure is used for raytracing or acceleration structure updates it’s referenced bottom-level acceleration structures are present.

Deserialize only works on the same device and driver version otherwise results are undefined. This isn’t intended to be used for caching acceleration structures, as running a full acceleration structure build is likely to be faster than loading one from disk.
While intended for tools such as PIX for Windows, nothing stops any app from using this, though at least for now deserialization requires the OS to be in developer mode.

The source memory must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE.
The destination memory must be in state D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE.

## -remarks

## -see-also

