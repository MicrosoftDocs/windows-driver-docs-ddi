---
UID: NC:d3d12umddi.PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0053
title: PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0053 (d3d12umddi.h)
description: Takes a standard resource buffer as input and resolves it to the API specified format.
ms.assetid: 21f08954-572e-4f40-a6ab-b829be64b500
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0053 callback function"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0053"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0053
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0053 callback function

## -description

Takes a standard resource buffer as input and resolves it to the API specified format.

## -parameters

### -param hDrvCommandList

A handle to the driver command list.

### -param pOutputArguments

Pointer to a [D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053](ns-d3d12umddi-d3d12ddi_resolve_video_motion_vector_heap_output_0053.md) structure containing output arguments.

### -param pInputArguments

Pointer to a [D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_INPUT_0053](ns-d3d12umddi-d3d12ddi_resolve_video_motion_vector_heap_input_0053.md) structure containing input arguments.


## -prototype

```cpp
//Declaration

PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0053 Pfnd3d12ddiResolveVideoMotionVectorHeap0053; 

// Definition

VOID Pfnd3d12ddiResolveVideoMotionVectorHeap0053 
(
	D3D12DDI_HCOMMANDLIST hDrvCommandList
	CONST D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053 *pOutputArguments
	CONST D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_INPUT_0053 *pInputArguments
)
{...}

```

## -remarks

The resolve operation is expected to be a light-weight translation of hardware dependent output to the API specified format.

## -see-also

