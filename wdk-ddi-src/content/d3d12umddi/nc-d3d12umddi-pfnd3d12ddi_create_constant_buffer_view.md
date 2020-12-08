---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW
title: PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW (d3d12umddi.h)
description: Create constant buffer view.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW callback function"]
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
 - PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW
 - d3d12umddi/PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW callback function


## -description

Create constant buffer view.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDI_CONSTANT_BUFFER_VIEW_DESC structure.

### -param DestDescriptor

CPU descriptor handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW Pfnd3d12ddiCreateConstantBufferView; 

// Definition

VOID Pfnd3d12ddiCreateConstantBufferView 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDI_CONSTANT_BUFFER_VIEW_DESC *
	D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptor
)
{...}

PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW 


```

