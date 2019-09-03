---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_STATE_0001
title: PFND3D12DDI_CREATE_PIPELINE_STATE_0001 (d3d12umddi.h)
description: The pfnCreatePipelineState callback function creates a pipeline state.
ms.assetid: 64291d84-d4c1-4629-927f-a57364d2d8c4
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATE_PIPELINE_STATE_0001"
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
- PFND3D12DDI_CREATE_PIPELINE_STATE_0001
product: 
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# PFND3D12DDI_CREATE_PIPELINE_STATE_0001 callback function

## -description

The pfnCreatePipelineState callback function creates a pipeline state.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_PIPELINE_STATE_0001 Pfnd3d12ddiCreatePipelineState0001; 

// Definition

HRESULT Pfnd3d12ddiCreatePipelineState0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_PIPELINE_STATE_0001 *
)
{...}

PFND3D12DDI_CREATE_PIPELINE_STATE_0001 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

A value used to create a pipeline state.

## -returns

Returns HRESULT.
