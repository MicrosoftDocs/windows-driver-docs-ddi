---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYHEAPANDRESOURCE
title: PFND3D12DDI_DESTROYHEAPANDRESOURCE (d3d12umddi.h)
description: Destroy heap and resource.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_DESTROYHEAPANDRESOURCE callback function"]
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
 - PFND3D12DDI_DESTROYHEAPANDRESOURCE
 - d3d12umddi/PFND3D12DDI_DESTROYHEAPANDRESOURCE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROYHEAPANDRESOURCE
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_DESTROYHEAPANDRESOURCE callback function


## -description

Destroy heap and resource.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A heap handle.

### -param Arg3

A resource handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYHEAPANDRESOURCE Pfnd3d12ddiDestroyheapandresource; 

// Definition

VOID Pfnd3d12ddiDestroyheapandresource 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HHEAP
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_DESTROYHEAPANDRESOURCE 


```

## -remarks

## -see-also

