---
UID: NC:d3d12umddi.PFND3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054
title: PFND3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054
author: windows-driver-content
description: Performs a ray tracing acceleration structure build on the GPU.
ms.assetid: c85f6b3b-0420-4acd-8f4a-891e4432fb4a
ms.date: 
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
-	PFND3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054
product:
- Windows
targetos: Windows
---

# PFND3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054 callback function

## -description

BuildRaytracingAccelerationStructure performs a ray tracing acceleration structure build on the GPU.

## -prototype

```
//Declaration

PFND3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054 Pfnd3d12ddiBuildRaytracingAccelerationStructure0054; 

// Definition

VOID Pfnd3d12ddiBuildRaytracingAccelerationStructure0054 
(
	D3D12DDI_HCOMMANDLIST Arg1
	CONST D3D12DDIARG_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_0054 *
)
{...}

```

## -parameters

### -param Arg1

A handle to the command list.

### -param *

Description of the acceleration structure to build.


## -returns

Returns VOID.

## -remarks

Can be called on graphics or compute command lists but not from bundles.


## -see-also
