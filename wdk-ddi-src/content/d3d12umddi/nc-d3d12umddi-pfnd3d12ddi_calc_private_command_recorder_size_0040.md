---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040
title: PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040 (d3d12umddi.h)
description: Calculates the command recorder size.
ms.assetid: 3220b5c8-7911-41fc-a698-5163a61ad60a
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040 callback function"]
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
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040
product:
 - Windows
---

# PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040 callback function

## -description

Calculates the command recorder size.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATE_COMMAND_RECORDER_0040 structure that contains the arguments to create a command recorder.

## -returns

Returns SIZE_T that represents the size of the command recorder.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040 Pfnd3d12ddiCalcPrivateCommandRecorderSize0040;

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateCommandRecorderSize0040
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_COMMAND_RECORDER_0040 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040


```

## -see-also

