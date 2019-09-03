---
UID: NE:d3d12umddi.D3D12DDI_RAYTRACING_INSTANCE_FLAGS
title: D3D12DDI_RAYTRACING_INSTANCE_FLAGS (d3d12umddi.h)
description: Flag options when generating instance data on the CPU to upload to the GPU, during ray tracing acceleration structure build.
ms.assetid: 6b171e36-4b02-45b1-9f84-cfae92d118d4
ms.date: 10/19/2018
ms.topic: enum
f1_keywords:
 - "d3d12umddi/D3D12DDI_RAYTRACING_INSTANCE_FLAGS"
ms.keywords: D3D12DDI_RAYTRACING_INSTANCE_FLAGS, D3D12DDI_RAYTRACING_INSTANCE_FLAGS, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_RAYTRACING_INSTANCE_FLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RAYTRACING_INSTANCE_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_RAYTRACING_INSTANCE_FLAGS enumeration

## -description

Flag options when generating instance data on the CPU to upload to the GPU, during ray tracing acceleration structure build.

## -enum-fields

### -field D3D12DDI_RAYTRACING_INSTANCE_FLAG_NONE

No options specified.

### -field D3D12DDI_RAYTRACING_INSTANCE_FLAG_TRIANGLE_CULL_DISABLE

Disables culling for this instance. The [D3D12DDI_CULL_MODE](ne-d3d12umddi-d3d12ddi_cull_mode.md) enumeration flags D3D12DDI_CULL_MODE_FRONT and D3D12DDI_CULL_MODE_BACK will have no effect on this instance.

### -field D3D12DDI_RAYTRACING_INSTANCE_FLAG_TRIANGLE_FRONT_COUNTERCLOCKWISE

This flag reverses front and back facings, which is useful if for example, the application’s natural winding order differs from the default.
By default, a triangle is front facing if its vertices appear clockwise from the ray origin and back facing if its vertices appear counter-clockwise from the ray origin, in object space in a left-handed coordinate system.  
Since these winding direction rules are defined in object space, they are unaffected by instance transforms. For example, an instance transform matrix with negative determinant (e.g. mirroring some geometry), does not change the facing of the triangles within the instance. Per-geometry transforms, by contrast, (defined in [D3D12DDI_RAYTRACING_GEOMETRY_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_geometry_desc_0054.md)), get combined with the associated vertex data in object space, so a negative determinant matrix there does flip triangle winding

### -field D3D12DDI_RAYTRACING_INSTANCE_FLAG_FORCE_OPAQUE

The instance will act as if the [D3D12DDI_RAYTRACING_GEOMETRY_FLAGS enumeration](ne-d3d12umddi-d3d12ddi_raytracing_geometry_flags.md)'s D3D12DDI_RAYTRACING_GEOMETRY_FLAG_OPAQUE flag had been specified for all the geometries in the bottom-level acceleration structure referenced by the instance. 

Note that this behavior can be overridden by the ray flag D3D12DDI_RAYTRACING_INSTANCE_FLAG_FORCE_NON_OPAQUE. This flag is mutually exclusive to the D3D12DDI_RAYTRACING_INSTANCE_FLAG_FORCE_NON_OPAQUE flag.

### -field D3D12DDI_RAYTRACING_INSTANCE_FLAG_FORCE_NON_OPAQUE

The instance will act as if the [D3D12DDI_RAYTRACING_GEOMETRY_FLAGS enumeration](ne-d3d12umddi-d3d12ddi_raytracing_geometry_flags.md)'s D3D12DDI_RAYTRACING_GEOMETRY_FLAG_OPAQUE flag had not been specified for any of the geometries in the bottom-level acceleration structure referenced by the instance. 

Note that this behavior can be overridden by the ray flag D3D12DDI_RAYTRACING_INSTANCE_FLAG_FORCE_OPAQUE. This flag is mutually exclusive to the D3D12DDI_RAYTRACING_INSTANCE_FLAG_FORCE_OPAQUE flag.


## -remarks

This enumeration is used in the [D3D12DDI_RAYTRACING_INSTANCE_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_instance_desc_0054.md) structure to specify an option to apply to the instance.

## -see-also
