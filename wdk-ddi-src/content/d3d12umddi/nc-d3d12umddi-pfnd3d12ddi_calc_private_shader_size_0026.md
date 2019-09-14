---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0026
title: PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0026 (d3d12umddi.h)
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.
tech.root: display
ms.assetid: ea84faa8-df7d-41e3-8250-d11dd75531c8
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
targetos: Windows
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0026"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0026
product:
 - Windows
---

# PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0026 callback function

## -description

Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATE_SHADER_0026 structure.

## -returns

Returns SIZE_T.

## -prototype

```
//Declaration

PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0026 Pfnd3d12ddiCalcPrivateShaderSize0026; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateShaderSize0026 
(
	D3D12DDI_HDEVICE Arg1
	 const D3D12DDIARG_CREATE_SHADER_0026 *
)
{...}

```

## -remarks

## -see-also

