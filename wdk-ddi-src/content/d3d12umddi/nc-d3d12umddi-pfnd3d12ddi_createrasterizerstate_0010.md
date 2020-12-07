---
UID: NC:d3d12umddi.PFND3D12DDI_CREATERASTERIZERSTATE_0010
title: PFND3D12DDI_CREATERASTERIZERSTATE_0010 (d3d12umddi.h)
description: Creates a rasterizer state.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATERASTERIZERSTATE_0010 callback function"]
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
 - PFND3D12DDI_CREATERASTERIZERSTATE_0010
 - d3d12umddi/PFND3D12DDI_CREATERASTERIZERSTATE_0010
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATERASTERIZERSTATE_0010
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATERASTERIZERSTATE_0010 callback function


## -description

Creates a rasterizer state.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDI_RASTERIZER_DESC_0010 structure.

### -param Arg3

A handle to a rasterizer state.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATERASTERIZERSTATE_0010 Pfnd3d12ddiCreaterasterizerstate0010; 

// Definition

VOID Pfnd3d12ddiCreaterasterizerstate0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDI_RASTERIZER_DESC_0010 *
	 D3D12DDI_HRASTERIZERSTATE
)
{...}

PFND3D12DDI_CREATERASTERIZERSTATE_0010 


```

