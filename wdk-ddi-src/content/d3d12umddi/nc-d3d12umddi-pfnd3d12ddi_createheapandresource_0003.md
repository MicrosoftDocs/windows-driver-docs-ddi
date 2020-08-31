---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEHEAPANDRESOURCE_0003
title: PFND3D12DDI_CREATEHEAPANDRESOURCE_0003 (d3d12umddi.h)
description: Used to simultaneously create a heap and resource.
ms.assetid: 478dfbcd-4472-4469-bd6e-66d6f7b45a3a
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATEHEAPANDRESOURCE_0003 callback function"]
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
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0003
 - d3d12umddi/PFND3D12DDI_CREATEHEAPANDRESOURCE_0003
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0003
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATEHEAPANDRESOURCE_0003 callback function


## -description

Used to simultaneously create a heap and resource.

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).

### -param Arg2 

Arguments used to create a heap.

### -param D3D12DDI_HHEAP 

A handle to a heap.

### -param D3D12DDI_HRTRESOURCE 

The handle of the resource for the driver to use when it calls back into the runtime.

### -param Arg5 

Arguments used to create a resource.

### -param Arg6

Used to clear the values of the resource.

### -param D3D12DDI_HRESOURCE 

The handle of the resource.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEHEAPANDRESOURCE_0003 Pfnd3d12ddiCreateheapandresource0003; 

// Definition

HRESULT Pfnd3d12ddiCreateheapandresource0003 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATEHEAP_0001 *
	 D3D12DDI_HHEAP
	 D3D12DDI_HRTRESOURCE
	CONST D3D12DDIARG_CREATERESOURCE_0003 *
	CONST D3D12DDI_CLEAR_VALUES *
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_CREATEHEAPANDRESOURCE_0003 


```

