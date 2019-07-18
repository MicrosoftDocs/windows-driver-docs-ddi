---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0025
title: PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0025 (d3d12umddi.h)
description: The PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0025 callback function creates a depth stencil state.
ms.assetid: 4320ce96-7f31-462c-ad1b-9a30d714e4ec
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0025"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0025
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0025 callback function

## -description

The PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0025 callback function creates a depth stencil state.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0025 Pfnd3d12ddiCreatedepthstencilstate0025; 

// Definition

VOID Pfnd3d12ddiCreatedepthstencilstate0025 
(
	D3D12DDI_HDEVICE hDevice
	CONST D3D12DDI_DEPTH_STENCIL_DESC_0025 *pDepthStencilDesc
	D3D12DDI_HDEPTHSTENCILSTATE hDepthStencilState
)
{...}

```

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param pDepthStencilDesc

A pointer to a [D3D12DDI_DEPTH_STENCIL_DESC_0025](ns-d3d12umddi-d3d12ddi_depth_stencil_desc_0025.md) structure that describes the parameters that the user-mode display driver uses to create a depth stencil state. 

### -param hDepthStencilState

A handle to the driver's private data for the depth stencil state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's [CalcPrivateDepthStencilStateSize](nc-d3d12umddi-pfnd3d12ddi_calcprivatedepthstencilstatesize_0025.md) function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its depth stencil state object.

## -returns

Returns VOID.

## -remarks


## -see-also
