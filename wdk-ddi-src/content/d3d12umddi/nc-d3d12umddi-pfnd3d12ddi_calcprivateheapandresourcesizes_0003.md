---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003
title: PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003 (d3d12umddi.h)
description: Calculate private heap and resources.
ms.date: 05/24/2022
keywords: ["PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003 callback function"]
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
 - PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003 callback function

## -description

Calculate private heap and resources.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

Pointer to a D3D12DDIARG_CREATEHEAP_0001 structure.

### -param unnamedParam3

Pointer to a D3D12DDIARG_CREATERESOURCE_0003 structure.

## -returns

Returns D3D12DDI_HEAP_AND_RESOURCE_SIZES.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003 Pfnd3d12ddiCalcprivateheapandresourcesizes0003; 

// Definition

D3D12DDI_HEAP_AND_RESOURCE_SIZES Pfnd3d12ddiCalcprivateheapandresourcesizes0003 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATEHEAP_0001 *
	CONST D3D12DDIARG_CREATERESOURCE_0003 *
)
{...}

PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003 


```
