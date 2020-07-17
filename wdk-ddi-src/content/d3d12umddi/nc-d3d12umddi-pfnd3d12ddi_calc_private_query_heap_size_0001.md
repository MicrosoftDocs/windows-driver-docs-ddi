---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001
title: PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001 (d3d12umddi.h)
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a query.
ms.assetid: 9f438444-7eb1-47ba-9bc2-36603467a77f
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001 callback function"]
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
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001"
 - "PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001 callback function

## -description

Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a query.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Used to create a query heap.

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001 Pfnd3d12ddiCalcPrivateQueryHeapSize0001; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateQueryHeapSize0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_QUERY_HEAP_0001 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001 


```

