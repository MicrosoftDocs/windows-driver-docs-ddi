---
UID: NS:d3d12umddi.D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054
title: D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054 (d3d12umddi.h)
description: Describes a ray tracing pipeline configuration.
ms.assetid: 6b313ba9-39e5-4b7b-837f-2dbf919fe4ea
ms.date: 10/19/2018
keywords: ["D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054"
 - "D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054"
ms.keywords: D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054, D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054, 
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
req.typenames: D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_RAYTRACING_PIPELINE_CONFIG_0054 structure

## -description

Describes a ray tracing pipeline configuration.

## -struct-fields

### -field MaxTraceRecursionDepth

The limit on ray recursion for the ray tracing pipeline.

## -remarks

A ray tracing pipeline needs one ray tracing pipeline configuration. If multiple pipeline configurations are present they must all match in content.  There isn’t benefit to having this duplication. For example, defining it once per collection doesn’t help drivers do early shader compilation before creating a ray tracing pipeline. This is unlike [D3D12DDI_RAYTRACING_SHADER_CONFIG_0054](ns-d3d12umddi-d3d12ddi_raytracing_shader_config_0054.md), which does benefit from duplication per collection.

## -see-also
