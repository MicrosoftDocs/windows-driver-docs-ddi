---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_ROOT_SIGNATURE
title: PFND3D12DDI_DESTROY_ROOT_SIGNATURE (d3d12umddi.h)
description: Destroys a root signature.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_DESTROY_ROOT_SIGNATURE callback function"]
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
 - PFND3D12DDI_DESTROY_ROOT_SIGNATURE
 - d3d12umddi/PFND3D12DDI_DESTROY_ROOT_SIGNATURE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROY_ROOT_SIGNATURE
dev_langs:
 - c++
---

# PFND3D12DDI_DESTROY_ROOT_SIGNATURE callback function


## -description

Destroys a root signature.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

A root signature handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROY_ROOT_SIGNATURE Pfnd3d12ddiDestroyRootSignature; 

// Definition

VOID Pfnd3d12ddiDestroyRootSignature 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HROOTSIGNATURE
)
{...}

PFND3D12DDI_DESTROY_ROOT_SIGNATURE 


```

## -remarks

## -see-also

