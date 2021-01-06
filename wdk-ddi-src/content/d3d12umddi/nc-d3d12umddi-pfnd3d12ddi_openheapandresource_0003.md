---
UID: NC:d3d12umddi.PFND3D12DDI_OPENHEAPANDRESOURCE_0003
title: PFND3D12DDI_OPENHEAPANDRESOURCE_0003 (d3d12umddi.h)
description: Implemented by the client driver to open heap and resource.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_OPENHEAPANDRESOURCE_0003 callback function"]
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
 - PFND3D12DDI_OPENHEAPANDRESOURCE_0003
 - d3d12umddi/PFND3D12DDI_OPENHEAPANDRESOURCE_0003
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_OPENHEAPANDRESOURCE_0003
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_OPENHEAPANDRESOURCE_0003 callback function


## -description

Implemented by the client driver to open heap and resource.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_OPENHEAP_0003 structure.

### -param Arg3

A heap handle.

### -param Arg4

The handle of the resource for the driver to use when it calls back into the runtime.

### -param Arg5

A resource handle.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_OPENHEAPANDRESOURCE_0003 Pfnd3d12ddiOpenheapandresource0003; 

// Definition

HRESULT Pfnd3d12ddiOpenheapandresource0003 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OPENHEAP_0003 *
	 D3D12DDI_HHEAP
	 D3D12DDI_HRTRESOURCE
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_OPENHEAPANDRESOURCE_0003 


```

## -remarks

## -see-also

