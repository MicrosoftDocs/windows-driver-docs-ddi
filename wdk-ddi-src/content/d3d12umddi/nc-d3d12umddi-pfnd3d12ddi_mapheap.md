---
UID: NC:d3d12umddi.PFND3D12DDI_MAPHEAP
title: PFND3D12DDI_MAPHEAP (d3d12umddi.h)
description: Map heap.
ms.assetid: 2187b018-e5d2-4a82-8232-ba9f1ae3a988
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_MAPHEAP callback function"]
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
 - "d3d12umddi/PFND3D12DDI_MAPHEAP"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_MAPHEAP
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_MAPHEAP callback function

## -description

Map heap.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A heap handle.

### -param Arg3

Pointer.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_MAPHEAP Pfnd3d12ddiMapheap; 

// Definition

HRESULT Pfnd3d12ddiMapheap 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HHEAP
	VOID **
)
{...}

PFND3D12DDI_MAPHEAP 


```

## -remarks

## -see-also

