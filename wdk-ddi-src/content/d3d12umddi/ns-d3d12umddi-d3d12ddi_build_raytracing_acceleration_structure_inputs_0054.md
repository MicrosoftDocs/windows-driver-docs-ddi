---
UID: NS:d3d12umddi.D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054
title: D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054 (d3d12umddi.h)
description: Build inputs for the PFND3D12DDI_GET_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054 callback function.
ms.assetid: 6953a548-c97f-423f-9f9c-4c2077f5acc7
ms.date: 10/19/2018
keywords: ["D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054"
 - "D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054"
ms.keywords: D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054, D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054, 
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
req.typenames: D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054 structure

## -description

Build inputs for the [PFND3D12DDI_GET_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054](nc-d3d12umddi-pfnd3d12ddi_get_raytracing_acceleration_structure_prebuild_info_0054.md) callback function.

## -struct-fields

### -field Type

A [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE](ne-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_type.md) enumeration that specifies the type of ray tracing acceleration structure to build.

### -field Flags

A [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS](ne-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_build_flags.md) flag that specifies the build options.

### -field NumDescs

The acceleration structure update count.

### -field DescsLayout

A [D3D12DDI_ELEMENTS_LAYOUT](ne-d3d12umddi-d3d12ddi_elements_layout.md) that defines the geometry ordering in a bottom-level acceleration structure.

### -field InstanceDescs

A D3D12DDI_GPU_VIRTUAL_ADDRESS that defines the instance order in a top-level acceleration structure.

### -field pGeometryDescs

Pointer to a [D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_geometry_desc_0054.md) that defines the geometry description.

### -field ppGeometryDescs
 
Pointer to the D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054 pointer.

## -remarks

## -see-also
