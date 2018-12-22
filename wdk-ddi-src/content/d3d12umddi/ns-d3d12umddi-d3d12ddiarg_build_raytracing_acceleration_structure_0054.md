---
UID: NS:d3d12umddi.D3D12DDIARG_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054
title: D3D12DDIARG_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054
description: Arguments used to build a ray tracing acceleration structure.
ms.assetid: 5d8ed94d-cf46-41d8-ad8a-c2021d6fcf0b
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDIARG_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054, D3D12DDIARG_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDIARG_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDIARG_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054 structure

## -description

Description of the acceleration structure to build.

## -struct-fields

### -field DestAccelerationStructureData

Location to store the resulting acceleration structure from [BuildRaytracingAccelerationStructure](nc-d3d12umddi-pfnd3d12ddi_build_raytracing_acceleration_structure_0054.md). [GetRaytracingAccelerationStructurePrebuildInfo](nc-d3d12umddi-pfnd3d12ddi_get_raytracing_acceleration_structure_prebuild_info_0054.md) reports the amount of memory required for the result here, given a set of acceleration structure build parameters.  

The start address must be aligned to 256 bytes.

The memory pointed to must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE.

### -field Inputs

A [D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054](ns-d3d12umddi-d3d12ddi_build_raytracing_acceleration_structure_inputs_0054.md) structure that represents the ray tracing acceleration build inputs.

### -field SourceAccelerationStructureData

Address of an existing acceleration structure if an acceleration structure update like an incremental build is being requested, by setting D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_PERFORM_UPDATE in the [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS](ne-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_build_flags.md) enumeration. Otherwise, this address must be NULL.

If this address is the same as *DestAccelerationStructureData*, the update is to be performed in-place. Any other form of overlap of the source and destination memory is invalid and produces undefined behavior.

The address must be aligned to 256 bytes.

The memory pointed to must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE.

### -field ScratchAccelerationStructureData

Location where the build will store temporary data. [GetRaytracingAccelerationStructurePrebuildInfo](nc-d3d12umddi-pfnd3d12ddi_get_raytracing_acceleration_structure_prebuild_info_0054.md) reports the amount of scratch memory the implementation will need for a given set of acceleration structure build parameters.  

The start address must be aligned to 256 bytes. Contents of this memory going into a build on the GPU timeline are irrelevant and will not be preserved. After the build is complete on the GPU timeline, the memory is left with whatever undefined contents the build finished with.

The memory pointed to must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS.

### -field NumPostbuildInfoDescs

The number of contiguous [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_postbuild_info_desc_0054.md) structures.

### -field pPostbuildInfoDescs

Points to an array of *NumPostbuildInfoDescs* pointers to D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_DESC_0054 structures.

## -remarks

## -see-also
