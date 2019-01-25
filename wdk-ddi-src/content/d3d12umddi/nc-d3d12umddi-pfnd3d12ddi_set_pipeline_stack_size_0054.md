---
UID: NC:d3d12umddi.PFND3D12DDI_SET_PIPELINE_STACK_SIZE_0054
title: PFND3D12DDI_SET_PIPELINE_STACK_SIZE_0054 (d3d12umddi.h)
description: Sets the current pipeline stack size.
ms.assetid: 0925f8dc-0a20-43e5-8d2e-d47005e3b392
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_SET_PIPELINE_STACK_SIZE_0054
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_SET_PIPELINE_STACK_SIZE_0054 callback function

## -description

SetPipelineStackSize sets the current pipeline stack size.

## -prototype

```cpp
//Declaration

PFND3D12DDI_SET_PIPELINE_STACK_SIZE_0054 Pfnd3d12ddiSetPipelineStackSize0054; 

// Definition

void Pfnd3d12ddiSetPipelineStackSize0054 
(
	D3D12DDI_HSTATEOBJECT_0054 Arg1
	UINT Arg2
)
{...}

```

## -parameters

### -param Arg1

A handle to the state object.

### -param Arg2

Stack size in bytes to use during pipeline execution for each shader thread (of which there can be many thousands in flight on the GPU).

## -returns

Returns void.

## -remarks

SetPipelineStackSize and [GetPipelineStackSize](nc-d3d12umddi-pfnd3d12ddi_get_pipeline_stack_size_0054.md) or any use of ray tracing pipeline state objects, such as [DispatchRays](nc-d3d12umddi-pfnd3d12ddi_dispatch_rays_0054.md) are not re-entrant. This means that if calling any of these functions from separate threads, the app must synchronize on its own. Any given DispatchRays call or GetPipelineStackSize call uses or returns the most recent stack size setting.

The runtime drops calls to state objects other than ray tracing pipelines (such as collections).



## -see-also
