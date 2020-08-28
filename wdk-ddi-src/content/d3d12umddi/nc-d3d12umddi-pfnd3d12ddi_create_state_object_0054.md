---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_STATE_OBJECT_0054
title: PFND3D12DDI_CREATE_STATE_OBJECT_0054 (d3d12umddi.h)
description: Creates a state object.
ms.assetid: 2d818331-58bb-4530-921a-96a5cd404043
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATE_STATE_OBJECT_0054 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
 - PFND3D12DDI_CREATE_STATE_OBJECT_0054
 - d3d12umddi/PFND3D12DDI_CREATE_STATE_OBJECT_0054
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_STATE_OBJECT_0054
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATE_STATE_OBJECT_0054 callback function


## -description

Creates a state object. A state object represents a variable amount of configuration state, including shaders, that an application manages as a single unit and which is given to a driver atomically to process (e.g. compile/optimize) however it sees fit. State objects are built out of subobjects. A [subobject](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md) has a type and corresponding data.

## -parameters

### -param Arg1

Handle to the device.

### -param Arg2

Pointer to a [D3D12DDIARG_CREATE_STATE_OBJECT_0054](ns-d3d12umddi-d3d12ddiarg_create_state_object_0054.md) structure.

### -param Arg3

Handle to a runtime handle type state object.

### -param Arg4

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_STATE_OBJECT_0054 Pfnd3d12ddiCreateStateObject0054; 

// Definition

HRESULT Pfnd3d12ddiCreateStateObject0054 
(
	D3D12DDI_HDEVICE Arg1
	CONST D3D12DDIARG_CREATE_STATE_OBJECT_0054 *
	D3D12DDI_HSTATEOBJECT_0054 Arg2
	D3D12DDI_HRTSTATEOBJECT_0054 Arg3
)
{...}

```

## -remarks

## -see-also

