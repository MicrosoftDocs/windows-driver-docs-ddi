---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_STATE_0010
title: PFND3D12DDI_CREATE_PIPELINE_STATE_0010 (d3d12umddi.h)
description: The pfnCreatePipelineState callback function creates a pipeline state.
ms.assetid: 5117d701-25c0-4c9d-9672-63028925fd0e
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
-	PFND3D12DDI_CREATE_PIPELINE_STATE_0010
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATE_PIPELINE_STATE_0010 callback function

## -description

The pfnCreatePipelineState callback function creates a pipeline state.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_PIPELINE_STATE_0010 Pfnd3d12ddiCreatePipelineState0010; 

// Definition

HRESULT Pfnd3d12ddiCreatePipelineState0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_PIPELINE_STATE_0010 *
	 D3D12DDI_HPIPELINESTATE
)
{...}

PFND3D12DDI_CREATE_PIPELINE_STATE_0010 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

A value used to create a pipeline state.

### -param D3D12DDI_HPIPELINESTATE: 

The handle of the pipeline state for the driver to use when it calls back into the runtime.

## -returns

Returns HRESULT.
