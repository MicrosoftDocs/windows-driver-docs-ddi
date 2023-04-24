---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003
title: PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003 (d3d12umddi.h)
description: Learn more about the PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003 callback function.
ms.date: 02/28/2023
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

**PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003** calculates the number of bytes required for a private heap and resource.

## -parameters

### -param unnamedParam1

[in] A handle to the display device (graphics context).

### -param unnamedParam2

[in/optional] Pointer to a [**D3D12DDIARG_CREATEHEAP_0001**](ns-d3d12umddi-d3d12ddiarg_createheap_0001.md) structure that describes the heap.

### -param unnamedParam3

Pointer to a **D3D12DDIARG_CREATERESOURCE_0003** structure that describes the resource.

## -returns

Returns a [**D3D12DDI_HEAP_AND_RESOURCE_SIZES**](ns-d3d12umddi-d3d12ddi_heap_and_resource_sizes.md) structure that specifies the sizes of the heap and resource, in bytes.
