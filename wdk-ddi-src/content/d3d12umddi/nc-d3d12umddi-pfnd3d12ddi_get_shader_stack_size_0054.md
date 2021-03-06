---
UID: NC:d3d12umddi.PFND3D12DDI_GET_SHADER_STACK_SIZE_0054
title: PFND3D12DDI_GET_SHADER_STACK_SIZE_0054 (d3d12umddi.h)
description: Retrieves the amount of stack memory required to invoke a ray tracing shader in HLSL.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_GET_SHADER_STACK_SIZE_0054 callback function"]
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
 - PFND3D12DDI_GET_SHADER_STACK_SIZE_0054
 - d3d12umddi/PFND3D12DDI_GET_SHADER_STACK_SIZE_0054
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_GET_SHADER_STACK_SIZE_0054
dev_langs:
 - c++
---

# PFND3D12DDI_GET_SHADER_STACK_SIZE_0054 callback function


## -description

Retrieves the amount of stack memory required to invoke a ray tracing shader in HLSL (High-Level Shader Language). Ray generation shaders may return nonzero despite being at the bottom of the stack.

## -parameters

### -param unnamedParam1

A handle to the state object.

### -param pExportName

Shader entry point in the state object for which to retrieve stack size.

## -returns

Returns the amount of stack, in bytes, required to invoke the shader.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GET_SHADER_STACK_SIZE_0054 Pfnd3d12ddiGetShaderStackSize0054; 

// Definition

UINT Pfnd3d12ddiGetShaderStackSize0054 
(
	D3D12DDI_HSTATEOBJECT_0054 Arg1
	LPCWSTR pExportName
)
{...}

```

## -remarks

## -see-also

