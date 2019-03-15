---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_COMMAND_POOL_SIZE_0040
title: PFND3D12DDI_CALC_PRIVATE_COMMAND_POOL_SIZE_0040 (d3d12umddi.h)
description: Calculates the size of the command pool for display.
ms.assetid: e2ea4d46-52df-4173-8b91-438bc5b02283
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
topic_type:
- apiref
api_type:
- UserDefined
api_location:
- d3d12umddi.h
api_name:
- PFND3D12DDI_CALC_PRIVATE_COMMAND_POOL_SIZE_0040
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CALC_PRIVATE_COMMAND_POOL_SIZE_0040 callback function

## -description

Calculates the size of the command pool for display.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_COMMAND_POOL_SIZE_0040 Pfnd3d12ddiCalcPrivateCommandPoolSize0040;

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateCommandPoolSize0040
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_COMMAND_POOL_0040 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_COMMAND_POOL_SIZE_0040


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param D3D12DDIARG_CREATE_COMMAND_POOL_0040

A pointer to the D3D12DDIARG_CREATE_COMMAND_POOL_0040 structure that contains arguments to create a command pool.

## -returns

Returns SIZE_T that represents the size of the command pool.




## -see-also
