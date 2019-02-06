---
UID: NC:d3d12umddi.PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010
title: PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010 (d3d12umddi.h)
description: Adds the input pipeline state to the corresponding library.
ms.assetid: b7f4ac02-7138-420f-b633-8f93fd7b5b86
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
-	PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010 callback function

## -description

Adds the input pipeline state to the corresponding library.

## -prototype

```cpp
//Declaration

PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010 Pfnd3d12ddiAddPipelineStateToLibrary0010; 

// Definition

HRESULT Pfnd3d12ddiAddPipelineStateToLibrary0010 
(
	D3D12DDI_HDEVICE hDevice
	D3D12DDI_HPIPELINELIBRARY hLibrary
	D3D12DDI_HPIPELINESTATE hPipelineState
	UINT PipelineIndex
)
{...}

PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010 


```

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hLibrary

The user mode driver handle type library.

### -param hPipelineState

A handle to the state of the pipeline.

### -param PipelineIndex: 

The pipeline index.

## -returns

Returns HRESULT.

## -remarks



## -see-also
