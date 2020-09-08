---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0025
title: PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0025 (d3d12umddi.h)
description: The CalcPrivateDepthStencilStateSize function determines the size of the user-mode display driver's private region of memory for a depth stencil state.
ms.assetid: 140b2f75-3201-47dc-83ea-a51f3ed61747
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0025 callback function"]
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
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0025
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0025
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0025
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0025 callback function


## -description

The **CalcPrivateDepthStencilStateSize** function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil state.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A pointer to a [D3D12DDI_DEPTH_STENCIL_DESC_0025](ns-d3d12umddi-d3d12ddi_depth_stencil_desc_0025.md) structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

Returns the size of the memory region that the driver requires for creating a depth stencil state.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0025 Pfnd3d12ddiCalcprivatedepthstencilstatesize0025; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatedepthstencilstatesize0025 
(
	D3D12DDI_HDEVICE hDevice
	CONST D3D12DDI_DEPTH_STENCIL_DESC_0025 *pDepthStencilDesc
)
{...}

```

## -see-also

