---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_QUERY_HEAP
title: PFND3D12DDI_DESTROY_QUERY_HEAP (d3d12umddi.h)
description: Destroys the query heap.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_DESTROY_QUERY_HEAP callback function"]
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
 - PFND3D12DDI_DESTROY_QUERY_HEAP
 - d3d12umddi/PFND3D12DDI_DESTROY_QUERY_HEAP
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROY_QUERY_HEAP
dev_langs:
 - c++
---

# PFND3D12DDI_DESTROY_QUERY_HEAP callback function


## -description

Destroys the query heap.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

A query heap handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROY_QUERY_HEAP Pfnd3d12ddiDestroyQueryHeap; 

// Definition

VOID Pfnd3d12ddiDestroyQueryHeap 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HQUERYHEAP
)
{...}

PFND3D12DDI_DESTROY_QUERY_HEAP 


```

## -remarks

## -see-also

