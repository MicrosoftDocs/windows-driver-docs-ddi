---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_QUERY_HEAP_0001
title: PFND3D12DDI_CREATE_QUERY_HEAP_0001 (d3d12umddi.h)
description: Creates a query heap.
ms.assetid: e41fa597-73da-4498-a59d-9fd1249e4020
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATE_QUERY_HEAP_0001"
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
- PFND3D12DDI_CREATE_QUERY_HEAP_0001
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATE_QUERY_HEAP_0001 callback function

## -description

Creates a query heap.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_QUERY_HEAP_0001 Pfnd3d12ddiCreateQueryHeap0001; 

// Definition

HRESULT Pfnd3d12ddiCreateQueryHeap0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_QUERY_HEAP_0001 *
	 D3D12DDI_HQUERYHEAP
)
{...}

PFND3D12DDI_CREATE_QUERY_HEAP_0001 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_CREATE_QUERY_HEAP_0001 structure.

### -param D3D12DDI_HQUERYHEAP: 

A query heap handle.

## -returns

Returns HRESULT.
