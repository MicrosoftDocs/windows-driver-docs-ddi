---
UID: NC:d3d12umddi.PFND3D12DDI_GET_PIPELINE_STACK_SIZE_0054
title: PFND3D12DDI_GET_PIPELINE_STACK_SIZE_0054
author: windows-driver-content
description: Retrieves the current pipeline stack size.
ms.assetid: fab470e7-e0bf-4648-bc28-49b13e47add2
ms.date: 
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
-	PFND3D12DDI_GET_PIPELINE_STACK_SIZE_0054
product:
-	Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_GET_PIPELINE_STACK_SIZE_0054 callback function

## -description

GetPipelineStackSize retrieves the current pipeline stack size.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GET_PIPELINE_STACK_SIZE_0054 Pfnd3d12ddiGetPipelineStackSize0054; 

// Definition

UINT Pfnd3d12ddiGetPipelineStackSize0054 
(
	D3D12DDI_HSTATEOBJECT_0054 Arg1
)
{...}

```

## -parameters

### -param Arg1: 

A handle to the state object.

## -returns

Returns UINT that represents the current pipeline stack size in bytes. If called on non-executable state objects (e.g. collections), the return value is 0.

## -remarks

GetPipelineStackSize and [SetPipelineStackSize](nc-d3d12umddi-pfnd3d12ddi_set_pipeline_stack_size_0054.md) are not re-entrant. This means that if calling either or both from separate threads, the app must synchronize on its own.


## -see-also
