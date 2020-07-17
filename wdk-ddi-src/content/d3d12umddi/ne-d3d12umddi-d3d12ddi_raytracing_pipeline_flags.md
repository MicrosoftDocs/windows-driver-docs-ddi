---
UID: NE:d3d12umddi.D3D12DDI_RAYTRACING_PIPELINE_FLAGS
title: D3D12DDI_RAYTRACING_PIPELINE_FLAGS
ms.date: 03/24/2020
ms.topic: language-reference
ms.assetid: 3e96d822-d211-46e3-b987-56924d332b95
tech.root: display
targetos: Windows
description: Raytracing pipeline flag.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RAYTRACING_PIPELINE_FLAGS
f1_keywords:
 - d3d12umddi/D3D12DDI_RAYTRACING_PIPELINE_FLAGS
 - ""
dev_langs:
 - c++
---

## -description

Raytracing pipeline flag.

## -enum-fields

### -field D3D12DDI_RAYTRACING_PIPELINE_FLAG_NONE

No additional ray flags.

### -field D3D12DDI_RAYTRACING_PIPELINE_FLAG_SKIP_TRIANGLES

For any [**TraceRay**](https://docs.microsoft.com/windows/win32/direct3d12/traceray-function) call within this raytracing pipeline, add in the RAY_FLAG_SKIP_TRIANGLES Ray flag. The resulting combination of ray flags must be valid. Implementations may be able to optimize pipelines knowing that a particular primitive type need not be considered.

### -field D3D12DDI_RAYTRACING_PIPELINE_FLAG_SKIP_PROCEDURAL_PRIMITIVES

For any [**TraceRay**](https://docs.microsoft.com/windows/win32/direct3d12/traceray-function) call within this raytracing pipeline, add in the RAY_FLAG_SKIP_PROCEDURAL_PRIMITIVES Ray flag. The resulting combination of ray flags must be valid. Implementations may be able to optimize pipelines knowing that a particular primitive type need not be considered.

## -remarks

A **D3D12DDI_RAYTRACING_PIPELINE_FLAGS** value is specified in [**D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075**](ns-d3d12umddi-d3d12ddi_raytracing_pipeline_config_0075.md).

See the [DirectX Raytracing (DXR) functional specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

## -see-also

[**D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0075**](ns-d3d12umddi-d3d12ddi_raytracing_pipeline_config_0075.md)
