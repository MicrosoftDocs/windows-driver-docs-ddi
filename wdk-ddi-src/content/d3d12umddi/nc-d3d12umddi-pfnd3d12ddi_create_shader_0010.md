---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_SHADER_0010
title: PFND3D12DDI_CREATE_SHADER_0010 (d3d12umddi.h)
description: Create shader.
ms.assetid: 56c7add3-70b2-4a2b-9412-ed7d3a839592
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATE_SHADER_0010"
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
- PFND3D12DDI_CREATE_SHADER_0010
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATE_SHADER_0010 callback function

## -description

Create shader.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_SHADER_0010 Pfnd3d12ddiCreateShader0010; 

// Definition

VOID Pfnd3d12ddiCreateShader0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_SHADER_0010 *
	 D3D12DDI_HSHADER
)
{...}

PFND3D12DDI_CREATE_SHADER_0010 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_CREATE_SHADER_0010 structure.

### -param D3D12DDI_HSHADER: 

Shader handle.

## -returns

Returns VOID.
