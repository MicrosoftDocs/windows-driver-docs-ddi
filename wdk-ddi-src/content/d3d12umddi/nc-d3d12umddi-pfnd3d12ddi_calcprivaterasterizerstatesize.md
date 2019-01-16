---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE
title: PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE
description: The CalcPrivateRasterizerStateSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a rasterizer state.
tech.root: display
ms.assetid: 73e36761-ac4e-45e1-8ad4-2d23fee52777
ms.date: 11/28/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
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
 - PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE callback function

## -description

The CalcPrivateRasterizerStateSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a rasterizer state.

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE Pfnd3d12ddiCalcprivaterasterizerstatesize; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivaterasterizerstatesize 
(
	D3D12DDI_HDEVICE Arg1
	 const D3D12DDI_RASTERIZER_DESC *
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param *

Pointer to a D3D12DDI_RASTERIZER_DESC structure.

## -returns

Returns SIZE_T.

## -remarks



## -see-also
