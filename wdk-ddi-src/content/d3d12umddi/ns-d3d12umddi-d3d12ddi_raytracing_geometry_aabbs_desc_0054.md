---
UID: NS:d3d12umddi.D3D12DDI_RAYTRACING_GEOMETRY_AABBS_DESC_0054
title: D3D12DDI_RAYTRACING_GEOMETRY_AABBS_DESC_0054 (d3d12umddi.h)
description: Describes a ray tracing AABB (axis-aligned bounding box) geometry.
ms.assetid: 853f77f7-1306-427d-a2bd-85f4adccb153
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_RAYTRACING_GEOMETRY_AABBS_DESC_0054"
ms.keywords: D3D12DDI_RAYTRACING_GEOMETRY_AABBS_DESC_0054, D3D12DDI_RAYTRACING_GEOMETRY_AABBS_DESC_0054, 
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
req.typenames: D3D12DDI_RAYTRACING_GEOMETRY_AABBS_DESC_0054
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RAYTRACING_GEOMETRY_AABBS_DESC_0054
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_RAYTRACING_GEOMETRY_AABBS_DESC_0054 structure

## -description

Describes a ray tracing AABB (axis-aligned bounding box) geometry.

## -struct-fields

### -field AABBCount

The number of AABBs pointed to in the contiguous array at AABBs.

### -field AABBs
 
A [D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE](ns-d3d12umddi-d3d12ddi_gpu_virtual_address_and_stride.md) structure describing the GPU memory location where an array of AABB descriptions is to be found, including the data stride between AABBs. The address and stride must each be aligned to 4 bytes.  The stride can be 0. The memory pointed to must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE.

## -remarks

## -see-also
