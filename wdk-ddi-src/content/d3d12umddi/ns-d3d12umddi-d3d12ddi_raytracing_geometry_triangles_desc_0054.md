---
UID: NS:d3d12umddi.D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054
title: D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054 (d3d12umddi.h)
description: Describes a ray tracing triangle geometry.
ms.assetid: bd34c803-32d9-4976-bce7-adc492c36a47
ms.date: 10/19/2018
keywords: ["D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054"
ms.keywords: D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054, D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054, 
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
req.typenames: D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_RAYTRACING_GEOMETRY_TRIANGLES_DESC_0054 structure

## -description

Describes a ray tracing triangle geometry.

## -struct-fields

### -field ColumnMajorTransform3x4

Address of a 3x4 affine transform matrix in row major layout to be applied to the vertices in the *VertexBuffer* during an acceleration structure build. The contents of *VertexBuffer* are not modified. If a 2D vertex format is used, the transformation is applied with the third vertex component assumed to be zero. 

If ColumnMajorTransform3x4 is NULL the vertices will not be transformed. Using ColumnMajorTransform3x4 may result in increased computation and/or memory requirements for the acceleration structure build.

The memory pointed to must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE.

### -field IndexFormat

A [DXGI_FORMAT](https://docs.microsoft.com/windows/desktop/api/dxgiformat/ne-dxgiformat-dxgi_format), representing the format of the indices in *IndexBuffer*. This value must be one of the following:

* DXGI_FORMAT_UNKNOWN (when *IndexBuffer* is NULL)
* DXGI_FORMAT_R32_UINT
* DXGI_FORMAT_R16_UINT

### -field VertexFormat

A [DXGI_FORMAT](https://docs.microsoft.com/windows/desktop/api/dxgiformat/ne-dxgiformat-dxgi_format), representing the format of the vertices (positions) in *VertexBuffer*. This value must be one of the following:

* DXGI_FORMAT_R32G32_FLOAT (third component assumed 0)
* DXGI_FORMAT_R32G32B32_FLOAT
* DXGI_FORMAT_R16G16_FLOAT (third component assumed 0)
* DXGI_FORMAT_R16G16B16A16_FLOAT 

### -field IndexCount

Number of indices in *IndexBuffer*. Must be 0 if *IndexBuffer* is NULL.

### -field VertexCount

Number of vertices (positions) in *VertexBuffer*.

### -field IndexBuffer

Array of vertex indices. If NULL, triangles are non-indexed. The address must be aligned to the size of *IndexFormat*.

The memory pointed to must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE. 

### -field VertexBuffer

Array of vertices including a stride. The alignment on the address and stride must be a multiple of the component size, meaning, 4 bytes for formats with 32-bit components and 2 bytes for formats with 16-bit components. There is no constraint on the stride (whereas there is a limit for graphics), other than that the bottom 32-bits of the value are all that are used. This means that the field is UINT64 purely to make neighboring fields align cleanly and obviously everywhere. Each vertex position is expected to be at the start address of the stride range and any excess space is ignored by acceleration structure builds. This excess space might contain other app data such as vertex attributes, which the app is responsible for manually fetching in shaders, whether it is interleaved in vertex buffers or elsewhere.

The memory pointed to must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE.

## -remarks

The geometry pointed to by this structure is always in triangle list from (indexed or non-indexed form). Strips are not supported.

## -see-also
