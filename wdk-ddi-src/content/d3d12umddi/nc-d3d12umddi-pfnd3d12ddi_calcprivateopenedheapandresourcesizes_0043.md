---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043
title: PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043 (d3d12umddi.h)
description: Calculates sizes for private opened heap and resources.
ms.assetid: af4c6fb0-a10f-4abe-8161-2df2563b76cd
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043 callback function"]
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
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043"
 - "PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043
product:
 - Windows
---

# PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043 callback function

## -description

Pointer to a CalcPrivateOpenedHeapAndResourceSizes function that calculates sizes for private opened heap and resources.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Open heap and resource.

### -param Arg3

The protected resource session.

## -returns

Returns D3D12DDI_HEAP_AND_RESOURCE_SIZES that contains the sizes for private opened heap and resources.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043 Pfnd3d12ddiCalcprivateopenedheapandresourcesizes0043;

// Definition

D3D12DDI_HEAP_AND_RESOURCE_SIZES Pfnd3d12ddiCalcprivateopenedheapandresourcesizes0043
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OPENHEAP_0003 *
	 D3D12DDI_HPROTECTEDRESOURCESESSION_0030
)
{...}

PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043


```

## -remarks

## -see-also

