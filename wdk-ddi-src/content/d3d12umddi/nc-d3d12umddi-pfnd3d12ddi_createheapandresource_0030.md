---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
title: PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 (d3d12umddi.h)
description: The PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 callback function simultaneously creates a heap and resource.
old-location: display\pfnd3d12ddi_createheapandresource_0030.htm
ms.date: 02/24/2023
keywords: ["PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 callback function"]
ms.keywords: PFND3D12DDI_CREATEHEAPANDRESOURCE_0030, PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 callback, PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEHEAPANDRESOURCE_0030, display.pfnd3d12ddi_createheapandresource_0030
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
 - d3d12umddi/PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
---

# PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 callback function

## -description

A user-mode display driver's **PFND3D12DDI_CREATEHEAPANDRESOURCE_0030** function simultaneously creates a heap and resource.

## -parameters

### -param unnamedParam1

A **D3D12DDI_HDEVICE** handle to the display device (graphics context).

### -param unnamedParam2

A [**D3D12DDIARG_CREATEHEAP_0001**](ns-d3d12umddi-d3d12ddiarg_createheap_0001.md) structure with arguments used to create a heap.

### -param unnamedParam3

A **D3D12DDI_HHEAP** handle to a heap.

### -param unnamedParam4

The **D3D12DDI_HRTRESOURCE** handle of the resource for the driver to use when it calls back into the runtime.

### -param unnamedParam5

Pointer to a [**D3D12DDIARG_CREATERESOURCE_0003**](ns-d3d12umddi-d3d12ddiarg_createresource_0003.md) structure containing the arguments used to create a resource.

### -param unnamedParam6

Pointer to a [**D3D12DDI_CLEAR_VALUES**](ns-d3d12umddi-d3d12ddi_clear_values.md) structure with values used to optimize clear operations for the resource.

### -param unnamedParam7

A **D3D12DDI_HPROTECTEDRESOURCESESSION_0030** handle to the protected resource session to use for the resource being created. Zero indicates unprotected resources. See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

### -param unnamedParam8

The **D3D12DDI_HRESOURCE** handle to the hardware resource.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

[**D3D12DDI_CLEAR_VALUES**](ns-d3d12umddi-d3d12ddi_clear_values.md)
