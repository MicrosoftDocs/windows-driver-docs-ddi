---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0001
title: PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0001 (d3d12umddi.h)
description: Used to calculate the pipeline state size.
ms.assetid: f7db5cd7-0b95-44f1-b855-e0e7f33eb910
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
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0001"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0001
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0001 callback function

## -description

Used to calculate the pipeline state size.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Used to create a pipeline state.

## -returns

The size in bytes of the state size.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0001 Pfnd3d12ddiCalcPrivatePipelineStateSize0001; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivatePipelineStateSize0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_PIPELINE_STATE_0001 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0001 


```

