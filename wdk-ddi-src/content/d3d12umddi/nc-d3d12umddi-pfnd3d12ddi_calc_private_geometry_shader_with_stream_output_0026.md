---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0026
title: PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0026
author: windows-driver-content
description: Calculates the geometry shader with stream output.
tech.root: display
ms.assetid: 91788a05-c3a3-4ec1-9eb2-809e7a891d50
ms.author: windowsdriverdev
ms.date: 11/28/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3d12umddi.h
api_name: 
 - PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0026
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0026 callback function

## -description

Calculates the geometry shader with stream output.

## -prototype

```
//Declaration

PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0026 Pfnd3d12ddiCalcPrivateGeometryShaderWithStreamOutput0026; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateGeometryShaderWithStreamOutput0026 
(
	D3D12DDI_HDEVICE Arg1
	const D3D12DDIARG_CREATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0026 *
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param *

Pointer to a D3D12DDIARG_CREATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0026 structure.

## -returns

Returns SIZE_T.

## -remarks



## -see-also