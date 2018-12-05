---
UID: NC:d3d12umddi.PFND3D12DDI_GET_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054
title: PFND3D12DDI_GET_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054
author: windows-driver-content
description: Queries the driver for resource requirements to build an acceleration structure.
ms.assetid: 09c3edcb-ed66-41ed-9db1-edca88369c43
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
-	PFND3D12DDI_GET_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_GET_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054 callback function

## -description

Queries the driver for resource requirements to build an acceleration structure.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GET_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054 Pfnd3d12ddiGetRaytracingAccelerationStructurePrebuildInfo0054; 

// Definition

void Pfnd3d12ddiGetRaytracingAccelerationStructurePrebuildInfo0054 
(
	D3D12DDI_HDEVICE Arg1
	CONST D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054 *
	D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054 *
)
{...}

```

## -parameters

### -param Arg1

A handle to the device.

### -param *

*_In_*

Pointer to a [D3D12DDI_BUILD_RAYTRACING_ACCELERATION_STRUCTURE_INPUTS_0054](ns-d3d12umddi-d3d12ddi_build_raytracing_acceleration_structure_inputs_0054.md) structure that contains the inputs. 

### -param *

*_Out_*

Pointer to a [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_PREBUILD_INFO_0054](ns-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_prebuild_info_0054.md) structure that contains prebuild info.

## -returns

Returns void.
The result of this callback function lets the application provide the correct amount of output storage and scratch storage to [BuildRaytracingAccelerationStructure](C:\Display\WorkingDDIs\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_build_raytracing_acceleration_structure_0054.md) given the same geometry.

## -remarks

This method is on the device as opposed to command list on the assumption that drivers must be able to calculate resource requirements for an acceleration structure build from only looking at the CPU visible portions of the call, without having to dereference any pointers to GPU memory containing actual vertex data, index data, etc.


## -see-also
