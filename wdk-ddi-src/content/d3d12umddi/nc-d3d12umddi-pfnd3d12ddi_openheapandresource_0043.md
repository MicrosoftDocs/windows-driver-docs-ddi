---
UID: NC:d3d12umddi.PFND3D12DDI_OPENHEAPANDRESOURCE_0043
title: PFND3D12DDI_OPENHEAPANDRESOURCE_0043 (d3d12umddi.h)
description: Implemented by the client driver to open heap and resource.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_OPENHEAPANDRESOURCE_0043 callback function"]
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
f1_keywords:
 - PFND3D12DDI_OPENHEAPANDRESOURCE_0043
 - d3d12umddi/PFND3D12DDI_OPENHEAPANDRESOURCE_0043
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_OPENHEAPANDRESOURCE_0043
product:
 - Windows
---

# PFND3D12DDI_OPENHEAPANDRESOURCE_0043 callback function


## -description

Implemented by the client driver to open heap and resource.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Open heap and resource.

### -param Arg3

Used to create a heap.

### -param Arg4

Used to create a resource.

### -param Arg5

The protected resource session.

### -param Arg6

The hardware resource.

## -returns

Returns STATUS_SUCCESS if completed successfully.

## -prototype

```cpp
//Declaration

PFND3D12DDI_OPENHEAPANDRESOURCE_0043 Pfnd3d12ddiOpenheapandresource0043;

// Definition

HRESULT Pfnd3d12ddiOpenheapandresource0043
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OPENHEAP_0003 *
	 D3D12DDI_HHEAP
	 D3D12DDI_HRTRESOURCE
	 D3D12DDI_HPROTECTEDRESOURCESESSION_0030
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_OPENHEAPANDRESOURCE_0043


```

## -see-also

