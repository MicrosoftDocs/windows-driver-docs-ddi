---
UID: NS:d3d12umddi.D3D12DDI_RAYTRACING_SHADER_CONFIG_0054
title: D3D12DDI_RAYTRACING_SHADER_CONFIG_0054
author: windows-driver-content
description: Describes the ray tracing shader configuration.
ms.assetid: a5bbfe65-1692-4fd4-b3ce-46b6df5a53ac
ms.date: 
ms.topic: struct
ms.keywords: D3D12DDI_RAYTRACING_SHADER_CONFIG_0054, D3D12DDI_RAYTRACING_SHADER_CONFIG_0054, 
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
req.typenames: D3D12DDI_RAYTRACING_SHADER_CONFIG_0054
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_RAYTRACING_SHADER_CONFIG_0054
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_RAYTRACING_SHADER_CONFIG_0054 structure

## -description

Describes the ray tracing shader configuration.

## -struct-fields

### -field MaxPayloadSizeInBytes

The maximum storage for scalars (counted as 4 bytes each) in ray payloads in ray tracing pipelines that contain this program.

### -field MaxAttributeSizeInBytes
 
The maximum number of scalars (counted as 4 bytes each) that can be used for attributes in pipelines that contain this shader. 

## -remarks

A ray tracing pipeline needs one ray tracing shader configuration. If multiple shader configurations are present, such as one in each collection to enable independent driver compilation for each one, they must all match when combined into a ray tracing pipeline.

## -see-also
