---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0001
title: PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0001
author: windows-driver-content
description: Determines the size of the user-mode display driver's private region of memory for a command list.
ms.assetid: a36c7d5c-6c17-4d57-be31-0ac527f56083
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0001
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0001 callback function

## -description

The CalcPrivateCommandListSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a command list.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0001 Pfnd3d12ddiCalcPrivateCommandListSize0001; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateCommandListSize0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_COMMAND_LIST_0001 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0001 


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param * 

A pointer to a D3D11DDIARG_CREATECOMMANDLIST structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

Returns SIZE_T.




## -see-also
