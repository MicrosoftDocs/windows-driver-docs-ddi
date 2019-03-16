---
UID: NC:d3d12umddi.PFND3D12DDI_SET_PIPELINE_STATE1_0054
title: PFND3D12DDI_SET_PIPELINE_STATE1_0054 (d3d12umddi.h)
description: Sets the pipeline state.
ms.assetid: 762c6ecc-061f-40ae-bcf6-7c7b527da106
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_SET_PIPELINE_STATE1_0054
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_SET_PIPELINE_STATE1_0054 callback function

## -description

Sets the pipeline state.

## -prototype

```cpp
//Declaration

PFND3D12DDI_SET_PIPELINE_STATE1_0054 Pfnd3d12ddiSetPipelineState10054; 

// Definition

VOID Pfnd3d12ddiSetPipelineState10054 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_HSTATEOBJECT_0054 Arg2
)
{...}

```

## -parameters

### -param Arg1

A handle to the command list.

### -param Arg2

A handle to the state object.

## -returns

Returns VOID.

## -remarks




## -see-also
