---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEHEAPANDRESOURCE_0075
title: PFND3D12DDI_CREATEHEAPANDRESOURCE_0075 (d3d12umddi.h)
description: Used to simultaneously create a heap and resource.
old-location: display\pfnd3d12ddi_createheapandresource_0075.htm
ms.assetid: 82922096-be52-433e-943b-af3f2a8fac79
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CREATEHEAPANDRESOURCE_0075 callback function"]
ms.keywords: PFND3D12DDI_CREATEHEAPANDRESOURCE_0075, PFND3D12DDI_CREATEHEAPANDRESOURCE_0075 callback, PFND3D12DDI_CREATEHEAPANDRESOURCE_0075 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEHEAPANDRESOURCE_0075, display.pfnd3d12ddi_createheapandresource_0075
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0075
 - d3d12umddi/PFND3D12DDI_CREATEHEAPANDRESOURCE_0075
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0075
---

# PFND3D12DDI_CREATEHEAPANDRESOURCE_0075 callback function


## -description

**PFND3D12DDI_CREATEHEAPANDRESOURCE_0075** is used to simultaneously create a heap and resource.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

[in, optional] D3D12DDIARG_CREATEHEAP_0001 arguments used to create a heap.

### -param Arg3

Handle used to create a heap.

### -param Arg4

Handle used to create a resource.

### -param Arg5

[in, optional] Pointer to a [**D3D12DDIARG_CREATERESOURCE_0075**](ns-d3d12umddi-d3d12ddiarg_createresource_0075.md) structure with arguments used to create a resource.

### -param Arg6

[in, optional] Pointer to a [**D3D12DDI_CLEAR_VALUES**](ns-d3d12umddi-d3d12ddi_clear_values.md) structure with values used to optimize clear operations for the resource.

### -param Arg7

The protected resource session to use for the heap/resource being created. Zero indicates unprotected resources.

### -param Arg8

The hardware resource.

## -returns

Returns STATUS_SUCCESS if completed successfully.

## -remarks

This user mode DDI for creating a heap and resources includes a protected resource handle.

See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -see-also

[**D3D12DDIARG_CREATERESOURCE_0075**](ns-d3d12umddi-d3d12ddiarg_createresource_0075.md)

[**D3D12DDI_CLEAR_VALUES**](ns-d3d12umddi-d3d12ddi_clear_values.md)

