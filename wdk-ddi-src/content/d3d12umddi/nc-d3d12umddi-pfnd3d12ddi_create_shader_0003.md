---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_SHADER_0003
title: PFND3D12DDI_CREATE_SHADER_0003
author: windows-driver-content
description: Create shader.
ms.assetid: 789087e8-bc98-4ccf-936e-cf880c89d176
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_CREATE_SHADER_0003
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATE_SHADER_0003 callback function

## -description

Create shader.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_SHADER_0003 Pfnd3d12ddiCreateShader0003; 

// Definition

VOID Pfnd3d12ddiCreateShader0003 
(
	 D3D12DDI_HDEVICE
	CONST UINT *pShaderCode
	 D3D12DDI_HROOTSIGNATURE
	 D3D12DDI_HSHADER
	CONST D3D12DDIARG_STAGE_IO_SIGNATURES *
	 D3D12DDI_CREATE_SHADER_FLAGS
)
{...}

PFND3D12DDI_CREATE_SHADER_0003 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param *pShaderCode

Pointer to the shader code.

### -param D3D12DDI_HROOTSIGNATURE

A root signature handle.

### -param D3D12DDI_HSHADER

A shader handle.

### -param * 

Pointer to a D3D12DDIARG_STAGE_IO_SIGNATURES structure.

### -param D3D12DDI_CREATE_SHADER_FLAGS: 

Flags to create a shader.

## -returns

Returns VOID.
