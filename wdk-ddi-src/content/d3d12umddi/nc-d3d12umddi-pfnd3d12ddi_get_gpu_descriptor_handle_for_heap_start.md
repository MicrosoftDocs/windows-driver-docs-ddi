---
UID: NC:d3d12umddi.PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
title: PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START (d3d12umddi.h)
description: Gets the GPU descriptor handle that represents the start of the heap.
ms.assetid: bffa5a27-4b90-4fb9-a121-4ecbe4813b10
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START callback function"]
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
 - "d3d12umddi/PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START callback function

## -description

Gets the GPU descriptor handle that represents the start of the heap.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A descriptor heap handle.

## -returns

Returns D3D12DDI_GPU_DESCRIPTOR_HANDLE.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START Pfnd3d12ddiGetGpuDescriptorHandleForHeapStart; 

// Definition

D3D12DDI_GPU_DESCRIPTOR_HANDLE Pfnd3d12ddiGetGpuDescriptorHandleForHeapStart 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HDESCRIPTORHEAP
)
{...}

PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START 


```

## -remarks

## -see-also

