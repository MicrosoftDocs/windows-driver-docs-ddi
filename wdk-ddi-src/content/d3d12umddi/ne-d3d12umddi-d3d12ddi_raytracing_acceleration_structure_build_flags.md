---
UID: NE:d3d12umddi.D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS
title: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS (d3d12umddi.h)
description: Specifies the ray tracing acceleration structure build flags.
ms.assetid: fd4d8fe1-c960-45b3-81d5-f05be42d5221
ms.date: 10/19/2018
ms.topic: enum
f1_keywords:
 - "d3d12umddi/D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS"
ms.keywords: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS, D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS enumeration

## -description

Specifies the ray tracing acceleration structure build flags.

## -enum-fields

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_NONE

No options specified for the acceleration structure build.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_ALLOW_UPDATE

Build the acceleration structure such that it supports future updates, via the flag D3D12_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_PERFORM_UPDATE, instead of the app having to entirely rebuild. This option may result in increased memory consumption and build times, and lower ray tracing performance. Future updates, however, should be faster than building the equivalent acceleration structure from scratch.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_ALLOW_COMPACTION

Enables the option to compact the acceleration structure by calling [CopyRaytracingAccelerationStructure](nc-d3d12umddi-pfnd3d12ddi_copy_raytracing_acceleration_structure_0054.md) with the compact mode. See [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE](ne-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_copy_mode.md).  
This option may result in increased memory consumption and build times. After future compaction, however, the resulting acceleration structure should consume a smaller memory footprint, no larger than building the acceleration structure from scratch.  

This flag is compatible with all other flags. If specified as part of an acceleration structure update, the source acceleration structure must have also been built with this flag.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_PREFER_FAST_TRACE

Construct a high quality acceleration structure that maximizes ray tracing performance at the expense of additional build time. A rough rule of thumb is that the implementation should take about 2-3 times the default build time in order to get better tracing performance. 

This flag is recommended for static geometry in particular. It is also compatible with all other flags except for D3D12_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_PREFER_FAST_BUILD.


### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_PREFER_FAST_BUILD

Construct a lower quality acceleration structure, trading ray tracing performance for build speed. A rough rule of thumb is that the implementation should take about 1/2 to 1/3 of the default build time at a sacrifice in tracing performance.

This flag is compatible with all other flags except for D3D12_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_PREFER_FAST_TRACE.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_MINIMIZE_MEMORY

Minimize the amount of scratch memory used during the acceleration structure build as well as the size of the result. This option may result in increased build times and/or ray tracing times.

This is orthogonal to the D3D12_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_ALLOW_COMPACTION flag, and explicit acceleration structure compaction that it enables. Combining the flags can mean both the initial acceleration structure as well as the result of compacting it uses less memory.
The impact of using this flag for a build is reflected in the result of calling [GetRaytracingAccelerationStructurePrebuildInfo](nc-d3d12umddi-pfnd3d12ddi_get_raytracing_acceleration_structure_prebuild_info_0054.md) before doing the build to retrieve memory requirements for the build.

This flag is compatible with all other flags.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_PERFORM_UPDATE

Perform an acceleration structure update, as opposed to building from scratch. This is faster than a full build, but can negatively impact ray tracing performance, especially if the positions of the underlying objects have changed significantly from the original build of the acceleration structure before updates.

If the addresses of the source and destination acceleration structures are identical, the update is performed in-place. Any other overlapping of address ranges of the source and destination is invalid. For non-overlapping source and destinations, the source acceleration structure is unmodified. The memory requirement for the output acceleration structure is the same as in the input acceleration structure.

This flag is compatible with all other flags. D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_ALLOW_UPDATE may or may not be set, it makes no difference because updates will continue to be allowed. The other flags selections, aside from D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_ALLOW_UPDATE and D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_PERFORM_UPDATE, must match the flags in the source acceleration structure.

Acceleration structure updates can be performed in unlimited succession. The source acceleration structure must have either been created with D3D12_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_ALLOW_UPDATE, D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_PERFORM_UPDATE, or if otherwise cloned, the originating acceleration structure had to have been produced in one of these ways. Essentially, the acceleration structure had to have been constructed with the expectation that updates can occur.

## -remarks

## -see-also
