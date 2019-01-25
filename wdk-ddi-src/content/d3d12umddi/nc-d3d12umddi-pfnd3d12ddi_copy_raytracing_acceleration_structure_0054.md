---
UID: NC:d3d12umddi.PFND3D12DDI_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054
title: PFND3D12DDI_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054 (d3d12umddi.h)
description: Copies a ray tracing acceleration structure.
ms.assetid: eb51f7de-53bd-4433-bf6b-d040020a8fc7
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054 callback function

## -description

Copies a ray tracing acceleration structure.

## -prototype

```cpp
//Declaration

PFND3D12DDI_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054 Pfnd3d12ddiCopyRaytracingAccelerationStructure0054; 

// Definition

VOID Pfnd3d12ddiCopyRaytracingAccelerationStructure0054 
(
	D3D12DDI_HCOMMANDLIST Arg1
	CONST D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054 *
)
{...}

```

## -parameters

### -param Arg1

A handle to a command list.

### -param *

Pointer to a [D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054](ns-d3d12umddi-d3d12ddiarg_copy_raytracing_acceleration_structure_0054.md) structure.

## -returns

Returns VOID.

## -remarks

Since ray tracing acceleration structures may contain internal pointers and have a device dependent opaque layout, copying them around or otherwise manipulating them requires a dedicated API so that drivers can handle the requested operation. The CopyRaytracingAccelerationStructure API takes a source acceleration structure and copies it to destination memory while applying the transformation requested by the Mode parameter.

Can be called on graphics or compute command lists but not from bundles.

## -see-also
