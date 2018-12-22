---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_STATE_OBJECT_SIZE_0054
title: PFND3D12DDI_CALC_PRIVATE_STATE_OBJECT_SIZE_0054
description: Calculates the private state object size.
ms.assetid: cfefa406-e5de-4256-be0c-97c6b62fb10d
ms.date: 10/19/2018
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: d3d12umddi.h
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
-	PFND3D12DDI_CALC_PRIVATE_STATE_OBJECT_SIZE_0054
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CALC_PRIVATE_STATE_OBJECT_SIZE_0054 callback function

## -description

Calculates the private state object size.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_STATE_OBJECT_SIZE_0054 Pfnd3d12ddiCalcPrivateStateObjectSize0054; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateStateObjectSize0054 
(
	D3D12DDI_HDEVICE Arg1
	CONST D3D12DDIARG_CREATE_STATE_OBJECT_0054 *
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param *

Pointer to a [D3D12DDIARG_CREATE_STATE_OBJECT_0054](ns-d3d12umddi-d3d12ddiarg_create_state_object_0054.md) structure that contains the arguments for a state object.



## -returns

Returns SIZE_T.

## -remarks



## -see-also
