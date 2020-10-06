---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW
title: PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW (d3d12umddi.h)
description: The PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW callback function creates a depth stencil view.
ms.assetid: e3973803-8c0d-4e73-b935-34bb6413d0d4
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW
 - d3d12umddi/PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW callback function


## -description

The PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW callback function creates a depth stencil view.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A pointer to a [D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW](ns-d3d12umddi-d3d12ddiarg_create_depth_stencil_view.md) structure that describes the parameters that the display driver uses to create a depth stencil view.

### -param DestDescriptor

A pointer to [D3D12DDI_CPU_DESCRIPTOR_HANDLE](ns-d3d12umddi-d3d12ddi_cpu_descriptor_handle.md) structure that describes the depth buffer bindings.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW Pfnd3d12ddiCreateDepthStencilView; 

// Definition

VOID Pfnd3d12ddiCreateDepthStencilView 
(
	D3D12DDI_HDEVICE hDevice
	CONST D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW *pCreateDepthStencilView
	D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptor
)
{...}

```

## -remarks

## -see-also

