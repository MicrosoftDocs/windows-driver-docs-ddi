---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_COMMAND_POOL_0040
title: PFND3D12DDI_CREATE_COMMAND_POOL_0040 (d3d12umddi.h)
description: Implemented by the client driver to create a command pool.
ms.assetid: 04cc7078-a69b-4783-adea-21131baf49dd
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
- PFND3D12DDI_CREATE_COMMAND_POOL_0040
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATE_COMMAND_POOL_0040 callback function

## -description

Implemented by the client driver to create a command pool.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_COMMAND_POOL_0040 Pfnd3d12ddiCreateCommandPool0040;

// Definition

HRESULT Pfnd3d12ddiCreateCommandPool0040
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_COMMAND_POOL_0040 *
	 D3D12DDI_HCOMMANDPOOL_0040
)
{...}

PFND3D12DDI_CREATE_COMMAND_POOL_0040


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param D3D12DDIARG_CREATE_COMMAND_POOL_0040

Pointer to a structure that contains arguments to create a command pool.

### -param D3D12DDI_HCOMMANDPOOL_0040

A handle to a command pool.



## -returns

Returns STATUS_SUCCESS if completed successfully.



## -see-also
