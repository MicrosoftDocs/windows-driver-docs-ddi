---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075
title: PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075 (d3d12umddi.h)
description: PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075 calculates private heap and resource sizes.
ms.assetid: a9818a14-c391-4d5c-afc2-9e846110b824
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075 callback function"]
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075"
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
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
- PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075
product: 
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom:
---

# PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075 callback function

## -description

**PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075** calculates private heap and resource sizes.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075 Pfnd3d12ddiCalcprivateheapandresourcesizes0075;

// Definition

D3D12DDI_HEAP_AND_RESOURCE_SIZES Pfnd3d12ddiCalcprivateheapandresourcesizes0075
(
    D3D12DDI_HDEVICE,
    CONST D3D12DDIARG_CREATEHEAP_0001 *,
    CONST D3D12DDIARG_CREATERESOURCE_0075 *,
    D3D12DDI_HPROTECTEDRESOURCESESSION_0030
)
{...}

PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0075


```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

[in, optional] Pointer to a D3D12DDIARG_CREATEHEAP_0001 structure.

### -param Arg3

[in, optional] Pointer to a [**D3D12DDIARG_CREATERESOURCE_0075**](ns-d3d12umddi-d3d12ddiarg_createresource_0075.md) structure.

### -param Arg4

The protected resource session to use for the heap/resource being created. Zero indicates unprotected resources.

## -returns

Returns D3D12DDI_HEAP_AND_RESOURCE_SIZES.

## -remarks

This user mode DDI for calculating heap and resource sizes includes a protected resource handle.

See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -see-also

[**D3D12DDIARG_CREATERESOURCE_0075**](ns-d3d12umddi-d3d12ddiarg_createresource_0075.md)
