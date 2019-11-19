---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP
title: PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP (d3d12umddi.h)
description: Destroys the descriptor heap.
ms.assetid: 05e4e853-9d81-4945-b223-a66e076bbac2
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
 - "d3d12umddi/PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP callback function

## -description

Destroys the descriptor heap.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A descriptor heap handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP Pfnd3d12ddiDestroyDescriptorHeap; 

// Definition

VOID Pfnd3d12ddiDestroyDescriptorHeap 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HDESCRIPTORHEAP
)
{...}

PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP 


```

