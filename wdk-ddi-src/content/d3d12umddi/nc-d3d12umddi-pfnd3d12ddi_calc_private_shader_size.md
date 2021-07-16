---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE
title: PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE (d3d12umddi.h)
description: The PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE callback function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.
tech.root: display
ms.date: 11/28/2018
keywords: ["PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE callback function"]
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
targetos: Windows
f1_keywords:
 - PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE
 - d3d12umddi/PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE
product:
 - Windows
---

# PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE callback function


## -description

Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param pShaderCode

Pointer to a shader code.

### -param unnamedParam3

A handle to a root signature.

### -param unnamedParam4

Pointer to a D3D12DDIARG_STAGE_IO_SIGNATURES structure.

## -returns

Returns SIZE_T.

## -prototype

```
//Declaration

PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE Pfnd3d12ddiCalcPrivateShaderSize; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateShaderSize 
(
	D3D12DDI_HDEVICE Arg1
	 const UINT *pShaderCode
	D3D12DDI_HROOTSIGNATURE Arg2
	 const D3D12DDIARG_STAGE_IO_SIGNATURES *
)
{...}

```

## -remarks

## -see-also

