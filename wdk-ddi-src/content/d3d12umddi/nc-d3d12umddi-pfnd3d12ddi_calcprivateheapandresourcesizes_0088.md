---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088
tech.root: display
title: PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088
ms.date: 09/22/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088 callback function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088
f1_keywords:
 - PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088
---

## -description

**PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088** calculates private heap and resource sizes.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

Pointer to a [**D3D12DDIARG_CREATEHEAP_0001**](ns-d3d12umddi-d3d12ddiarg_createheap_0001.md) structure that describes the heap.

### -param unnamedParam3

Pointer to a [**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md) structure.

### -param unnamedParam4

The protected resource session to use for the heap/resource being created. Zero indicates unprotected resources. See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -remarks

## -see-also

[**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md)
