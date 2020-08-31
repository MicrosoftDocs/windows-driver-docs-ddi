---
UID: NE:d3d12umddi.D3D12DDI_RAYTRACING_GEOMETRY_FLAGS
title: D3D12DDI_RAYTRACING_GEOMETRY_FLAGS (d3d12umddi.h)
description: Specifies the ray tracing geometry flags.
ms.assetid: cc2f1309-40c0-41de-af55-8265581794da
ms.date: 10/19/2018
keywords: ["D3D12DDI_RAYTRACING_GEOMETRY_FLAGS enumeration"]
ms.keywords: D3D12DDI_RAYTRACING_GEOMETRY_FLAGS, D3D12DDI_RAYTRACING_GEOMETRY_FLAGS,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_RAYTRACING_GEOMETRY_FLAGS
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RAYTRACING_GEOMETRY_FLAGS
 - d3d12umddi/D3D12DDI_RAYTRACING_GEOMETRY_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RAYTRACING_GEOMETRY_FLAGS
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_RAYTRACING_GEOMETRY_FLAGS enumeration


## -description

Specifies the ray tracing geometry flags.

## -enum-fields

### -field D3D12DDI_RAYTRACING_GEOMETRY_FLAG_NONE

No options specified.

### -field D3D12DDI_RAYTRACING_GEOMETRY_FLAG_OPAQUE

When rays encounter this geometry, the geometry acts as if no any hit shader is present. It is recommended to use this flag liberally, as it can enable important ray processing optimizations. 

> [!NOTE] 
> This behavior can be overridden on a per-instance basis with [D3D12DDI_RAYTRACING_INSTANCE_FLAGS](ne-d3d12umddi-d3d12ddi_raytracing_instance_flags.md), and on a per-ray basis using Ray flags in TraceRay().

### -field D3D12DDI_RAYTRACING_GEOMETRY_FLAG_NO_DUPLICATE_ANYHIT_INVOCATION

By default, the system is free to trigger an any hit shader more than once for a given ray-primitive intersection. This flexibility helps improve the traversal efficiency of acceleration structures in certain cases. For instance, if the acceleration structure is implemented internally with bounding volumes, the implementation may find it beneficial to store relatively long triangles in multiple bounding boxes rather than a larger single box.

However, some application use cases require that intersections be reported to any hit shader at most once. This flag enables that guarantee for the given geometry, potentially with some performance impact.

This flag applies to all geometry types.

## -remarks

## -see-also

