---
UID: NC:d3d12umddi.PFND3D12DDI_DISPATCH_RAYS_0054
title: PFND3D12DDI_DISPATCH_RAYS_0054 (d3d12umddi.h)
description: Launch threads of a ray generation shader.
ms.assetid: 89f29b62-d9da-4afb-a6d9-6c3584354f81
ms.date: 10/19/2018
ms.topic: callback
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
 - "d3d12umddi/PFND3D12DDI_DISPATCH_RAYS_0054"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DISPATCH_RAYS_0054
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_DISPATCH_RAYS_0054 callback function

## -description

Launch threads of a ray generation shader.

## -parameters

### -param Arg1

A handle to the command list.

### -param Arg2

Pointer to the [D3D12DDIARG_DISPATCH_RAYS_0054](ns-d3d12umddi-d3d12ddiarg_dispatch_rays_0054.md) structure.

## -returns

Returns VOID.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DISPATCH_RAYS_0054 Pfnd3d12ddiDispatchRays0054; 

// Definition

VOID Pfnd3d12ddiDispatchRays0054 
(
	D3D12DDI_HCOMMANDLIST Arg1
	CONST D3D12DDIARG_DISPATCH_RAYS_0054 *
)
{...}

```

## -remarks

This callback can be called from graphics or compute command lists and bundles.

PFND3D12DDI_DISPATCH_RAYS_0054 invokes a grid of ray generation shader invocations. Each invocation (thread) of a ray generation shader knows its location in the overall grid, can generate arbitrary rays via [PFND3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054](nc-d3d12umddi-pfnd3d12ddi_build_raytracing_acceleration_structure_0054.md), and operates independently of other invocations. So there is no defined order of execution of threads with respect to each other.

## -see-also

