---
UID: NC:d3d12umddi.PFND3D12DDI_CREATECOMMANDALLOCATOR
title: PFND3D12DDI_CREATECOMMANDALLOCATOR (d3d12umddi.h)
description: Creates a command allocator.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATECOMMANDALLOCATOR callback function"]
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
 - PFND3D12DDI_CREATECOMMANDALLOCATOR
 - d3d12umddi/PFND3D12DDI_CREATECOMMANDALLOCATOR
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATECOMMANDALLOCATOR
dev_langs:
 - c++
---

# PFND3D12DDI_CREATECOMMANDALLOCATOR callback function


## -description

Creates a command allocator.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

Pointer to a D3D12DDIARG_CREATECOMMANDALLOCATOR structure.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATECOMMANDALLOCATOR Pfnd3d12ddiCreatecommandallocator; 

// Definition

HRESULT Pfnd3d12ddiCreatecommandallocator 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATECOMMANDALLOCATOR *
)
{...}

PFND3D12DDI_CREATECOMMANDALLOCATOR 


```

