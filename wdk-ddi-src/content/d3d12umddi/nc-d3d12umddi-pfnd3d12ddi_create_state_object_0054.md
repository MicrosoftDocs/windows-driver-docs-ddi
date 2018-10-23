---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_STATE_OBJECT_0054
title: PFND3D12DDI_CREATE_STATE_OBJECT_0054
author: windows-driver-content
description: Creates a state object.
ms.assetid: 2d818331-58bb-4530-921a-96a5cd404043
ms.date: 10/19/2018
ms.topic: callback
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_CREATE_STATE_OBJECT_0054
product:
-	Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATE_STATE_OBJECT_0054 callback function

## -description

Creates a state object. A state object represents a variable amount of configuration state, including shaders, that an application manages as a single unit and which is given to a driver atomically to process (e.g. compile/optimize) however it sees fit. State objects are built out of subobjects. A [subobject](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md) has a type and corresponding data.

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

## -parameters

### -param Arg1

Handle to the device.

### -param *

Pointer to a [D3D12DDIARG_CREATE_STATE_OBJECT_0054](ns-d3d12umddi-d3d12ddiarg_create_state_object_0054.md) structure.

### -param Arg2

Handle to a state object.

### -param Arg3

Handle to a runtime handle type state object.

## -returns

Returns HRESULT.

## -remarks



## -see-also
