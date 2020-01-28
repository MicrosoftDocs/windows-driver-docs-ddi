---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE_0010
title: PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE_0010 (d3d12umddi.h)
description: Calculate the private rasterizer state size.
ms.assetid: b6ff00b0-7a72-4617-878b-b2c1b775999f
ms.date: 10/19/2018
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE_0010"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE_0010
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE_0010 callback function

## -description

Calculate the private rasterizer state size.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDI_RASTERIZER_DESC_0010 structure.

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE_0010 Pfnd3d12ddiCalcprivaterasterizerstatesize0010; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivaterasterizerstatesize0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDI_RASTERIZER_DESC_0010 *
)
{...}

PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE_0010 


```

