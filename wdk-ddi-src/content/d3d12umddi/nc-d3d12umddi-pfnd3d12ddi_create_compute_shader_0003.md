---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_COMPUTE_SHADER_0003
title: PFND3D12DDI_CREATE_COMPUTE_SHADER_0003 (d3d12umddi.h)
description: Create a compute shader.
ms.assetid: bd3eb1b9-3238-4e2a-89ed-f0fdf2f841bc
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATE_COMPUTE_SHADER_0003 callback function"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_CREATE_COMPUTE_SHADER_0003
 - d3d12umddi/PFND3D12DDI_CREATE_COMPUTE_SHADER_0003
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_COMPUTE_SHADER_0003
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATE_COMPUTE_SHADER_0003 callback function


## -description

Create a compute shader.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param pShaderCode

Pointer to a shader code.

### -param Arg3

A handle to a root signature.

### -param Arg4

A shader handle.

### -param Arg5

Flags to create a shader.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_COMPUTE_SHADER_0003 Pfnd3d12ddiCreateComputeShader0003; 

// Definition

VOID Pfnd3d12ddiCreateComputeShader0003 
(
	 D3D12DDI_HDEVICE
	CONST UINT *pShaderCode
	 D3D12DDI_HROOTSIGNATURE
	 D3D12DDI_HSHADER
	 D3D12DDI_CREATE_SHADER_FLAGS
)
{...}

PFND3D12DDI_CREATE_COMPUTE_SHADER_0003 


```

