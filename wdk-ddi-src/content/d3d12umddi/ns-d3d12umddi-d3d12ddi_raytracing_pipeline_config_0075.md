---
UID: NS:d3d12umddi.D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075
title: D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075
ms.date: 03/24/2020
tech.root: display
ms.topic: language-reference
targetos: Windows
description: D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075 describes a ray tracing pipeline configuration.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075
f1_keywords:
 - D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075
 - d3d12umddi/D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075
dev_langs:
 - c++
---

## -description

**D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075** describes a ray tracing pipeline configuration.

## -struct-fields

### -field MaxTraceRecursionDepth

The limit on ray recursion for the ray tracing pipeline.

### -field Flags

A [**D3D12DDI_RAYTRACING_PIPELINE_FLAGS**](ne-d3d12umddi-d3d12ddi_raytracing_pipeline_flags.md) value.

## -remarks

A ray tracing pipeline needs one ray tracing pipeline configuration. If multiple shader configurations are present (such as one in each collection to enable independent driver compilation for each one) they must all match when combined into a raytracing pipeline.

See the [DirectX Raytracing (DXR) functional specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

## -see-also

[**D3D12DDI_RAYTRACING_PIPELINE_FLAGS**](ne-d3d12umddi-d3d12ddi_raytracing_pipeline_flags.md)

