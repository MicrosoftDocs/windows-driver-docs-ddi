---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_SAMPLER
title: PFND3D12DDI_CREATE_SAMPLER (d3d12umddi.h)
description: Create sampler.
ms.assetid: b15f237f-2ef3-4b88-88cb-4a2f3c9e6fc9
ms.date: 10/19/2018
ms.topic: callback
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
 - "d3d12umddi/PFND3D12DDI_CREATE_SAMPLER"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_SAMPLER
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATE_SAMPLER callback function

## -description

Create sampler.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATE_SAMPLER structure.

### -param DestDescriptor

A CPU descriptor handle.

## -returns

Returns VOID.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_SAMPLER Pfnd3d12ddiCreateSampler; 

// Definition

VOID Pfnd3d12ddiCreateSampler 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_SAMPLER *
	D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptor
)
{...}

PFND3D12DDI_CREATE_SAMPLER 


```

