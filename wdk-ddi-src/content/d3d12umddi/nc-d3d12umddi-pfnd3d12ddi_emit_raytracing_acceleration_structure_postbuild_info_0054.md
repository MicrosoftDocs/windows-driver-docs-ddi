---
UID: NC:d3d12umddi.PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054
title: PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054 (d3d12umddi.h)
description: Emits post-build properties for a set of acceleration structures.
ms.assetid: ae08659a-7863-4998-82f2-275aaff4f386
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054"
 - "PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054 callback function

## -description

Emits post-build properties for a set of acceleration structures.

## -parameters

### -param Arg1

A handle to the command list.

### -param Arg2

Pointer to a [D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054](ns-d3d12umddi-d3d12ddiarg_emit_raytracing_acceleration_structure_postbuild_info_0054.md) structure.

## -prototype

```cpp
//Declaration

PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054 Pfnd3d12ddiEmitRaytracingAccelerationStructurePostbuildInfo0054; 

// Definition

VOID Pfnd3d12ddiEmitRaytracingAccelerationStructurePostbuildInfo0054 
(
	D3D12DDI_HCOMMANDLIST Arg1
	CONST D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054 *
)
{...}

```

## -remarks

Can be called on graphics or compute command lists but not from bundles.

## -see-also

