---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0010
title: PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0010 (d3d12umddi.h)
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.
ms.assetid: e0dff433-c376-40a9-a69c-3e5a5e76742d
ms.date: 10/19/2018
ms.topic: callback
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
- PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0010
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0010 callback function

## -description

Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0010 Pfnd3d12ddiCalcPrivateShaderSize0010; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateShaderSize0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_SHADER_0010 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0010 


```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param *

Used to create a shader.

## -returns

Returns SIZE_T.
