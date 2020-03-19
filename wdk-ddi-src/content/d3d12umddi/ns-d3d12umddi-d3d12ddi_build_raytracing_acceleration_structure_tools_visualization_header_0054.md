---
UID: NS:d3d12umddi.D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054
title: D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054 (d3d12umddi.h)
description: Describes the GPU memory layout of an acceleration structure visualization.
ms.assetid: 9dc734e8-c981-4707-b3a8-dc46d7d705dd
ms.date: 10/19/2018
keywords: ["D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054"
ms.keywords: D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054, D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054, 
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
req.typenames: D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_TOOLS_VISUALIZATION_HEADER_0054 structure

## -description

Describes the GPU memory layout of an acceleration structure visualization. 

## -struct-fields

### -field Type

A [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE](ne-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_type.md) enumeration.

### -field NumDescs
 
The number of either [D3D12DDI_RAYTRACING_INSTANCE_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_instance_desc_0054.md) InstanceDescs[**NumDescs**] or [D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_geometry_desc_0054.md) GeometryDescs[**NumDescs**], depending on the value of *Type*.

## -remarks

## -see-also
