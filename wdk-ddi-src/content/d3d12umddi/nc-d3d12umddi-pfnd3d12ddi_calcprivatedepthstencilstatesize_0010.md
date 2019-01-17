---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0010
title: PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0010
description: The CalcPrivateDepthStencilStateSize function determines the size of the user-mode display driver's private region of memory for a depth stencil state.
ms.assetid: f589834c-e00b-42cf-b76a-fdb4bf90e8a1
ms.date: 10/19/2018
ms.topic: callback
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0010
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0010 callback function

## -description

The **CalcPrivateDepthStencilStateSize** function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil state.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0010 Pfnd3d12ddiCalcprivatedepthstencilstatesize0010; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatedepthstencilstatesize0010 
(
	D3D12DDI_HDEVICE hDevice
	CONST D3D12DDI_DEPTH_STENCIL_DESC_0010 *pDepthStencilDesc
)
{...}

```

## -parameters

### -param hDevice

A handle to the display device (graphics context).


### -param pDepthStencilDesc

A pointer to a [D3D12DDI_DEPTH_STENCIL_DESC_0010](ns-d3d12umddi-d3d12ddi_depth_stencil_desc_0010.md) structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 

## -returns

Returns the size of the memory region that the driver requires for creating a depth stencil state.

## -remarks



## -see-also
