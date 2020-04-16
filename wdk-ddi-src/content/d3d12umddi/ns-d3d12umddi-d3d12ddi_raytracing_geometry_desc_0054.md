---
UID: NS:d3d12umddi.D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054
title: D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054 (d3d12umddi.h)
description: Describes a ray tracing geometry.
ms.assetid: a1950a04-049f-41c2-99ab-46d44a0b1cd6
ms.date: 10/19/2018
keywords: ["D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054"
ms.keywords: D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054, D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054, 
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
req.typenames: D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054 structure

## -description

Describes a ray tracing geometry.

## -struct-fields

### -field Type

A [D3D12DDI_RAYTRACING_GEOMETRY_TYPE](ne-d3d12umddi-d3d12ddi_raytracing_geometry_type.md) type.

### -field Flags

A [D3D12DDI_RAYTRACING_GEOMETRY_FLAGS](ne-d3d12umddi-d3d12ddi_raytracing_geometry_flags.md) flag.

### -field Triangles

A [D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_geometry_triangles_desc_0054.md) structure that describes a triangle geometry if *Type* is D3D12DDI_RAYTRACING_GEOMETRY_TYPE_TRIANGLES. Otherwise, this parameter is unused.

### -field AABBs
 
A [D3D12DDI_RAYTRACING_GEOMETRY_AABBS_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_geometry_aabbs_desc_0054.md) structure that describes an AABB (axis-aligned bounding box) geometry if *Type* is D3D12DDI_RAYTRACING_GEOMETRY_TYPE_PROCEDURAL_PRIMITIVE_AABBS. Otherwise, this parameter is unused.

## -remarks

## -see-also
