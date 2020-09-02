---
UID: NC:d3d12umddi.PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0060
title: PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0060
author: windows-driver-content
description: Takes a standard resource buffer as input and resolves it to the API specified format.
tech.root: display
ms.assetid: 45c9cf09-be26-45e3-a78f-c27778448da8
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0060 callback function"]
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
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
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0060
 - d3d12umddi/PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0060
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0060
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0060 callback function


## -description

Takes a standard resource buffer as input and resolves it to the API specified format.

## -parameters

### -param hDrvCommandList

A handle to the driver command list.

### -param pOutputArguments

Pointer to a [D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060](ns-d3d12umddi-d3d12ddi_resolve_video_motion_vector_heap_output_0060.md) structure containing output arguments.

### -param pInputArguments

Pointer to a [D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_INPUT_0053](ns-d3d12umddi-d3d12ddi_resolve_video_motion_vector_heap_input_0053.md) structure containing input arguments.

## -prototype

```
//Declaration

PFND3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_0060 Pfnd3d12ddiResolveVideoMotionVectorHeap0060; 

// Definition

VOID Pfnd3d12ddiResolveVideoMotionVectorHeap0060 
(
	D3D12DDI_HCOMMANDLIST hDrvCommandList
	 const D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060 *pOutputArguments
	 const D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_INPUT_0053 *pInputArguments
)
{...}

```

## -remarks

The resolve operation is expected to be a light-weight translation of hardware dependent output to the API specified format.

## -see-also

