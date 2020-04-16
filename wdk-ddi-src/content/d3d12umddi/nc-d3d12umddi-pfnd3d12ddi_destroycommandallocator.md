---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYCOMMANDALLOCATOR
title: PFND3D12DDI_DESTROYCOMMANDALLOCATOR (d3d12umddi.h)
description: Destroys a command allocator.
ms.assetid: c2d78cd5-3273-42eb-b069-bafdea236115
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_DESTROYCOMMANDALLOCATOR callback function"]
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
 - "d3d12umddi/PFND3D12DDI_DESTROYCOMMANDALLOCATOR"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROYCOMMANDALLOCATOR
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_DESTROYCOMMANDALLOCATOR callback function

## -description

Destroys a command allocator.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A handle to a command allocator.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYCOMMANDALLOCATOR Pfnd3d12ddiDestroycommandallocator; 

// Definition

VOID Pfnd3d12ddiDestroycommandallocator 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HCOMMANDALLOCATOR
)
{...}

PFND3D12DDI_DESTROYCOMMANDALLOCATOR 


```

## -remarks

## -see-also

