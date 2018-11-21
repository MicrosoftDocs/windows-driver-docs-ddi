---
UID: NS:d3d12umddi.D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054
title: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054
author: windows-driver-content
description: Contains memory requirements for a ray tracing acceleration structure build.
ms.assetid: bcad8b22-709a-44fb-85ed-4b9f723576a8
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054, D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054, 
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
req.typenames: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054 structure

## -description

Contains memory requirements for a ray tracing acceleration structure build.

## -struct-fields

### -field ResultDataMaxSizeInBytes

Size required to hold the result of an acceleration structure build based on the specified inputs.

### -field ScratchDataSizeInBytes

Scratch storage on the GPU that is required during acceleration structure build, based on the specified inputs.

### -field UpdateScratchDataSizeInBytes
 
Scratch storage on the GPU that is required during an acceleration structure update, based on the specified inputs. This only needs to be called for the original acceleration structure build, and defines the scratch storage requirement for every acceleration structure update other than the initial build.

If the D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAG_ALLOW_UPDATE flag is not specified in [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_BUILD_FLAGS](ne-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_build_flags.md), this parameter returns 0.

## -remarks

## -see-also
