---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010
title: PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010 (d3d12umddi.h)
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.
ms.assetid: 1b9a4131-0167-46db-a717-cfcbd3102cf7
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010 callback function"]
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
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010"
 - "PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010 callback function

## -description

The CalcPrivateBlendStateSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A pointer to a D3D12DDI_BLEND_DESC_0010 structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010 Pfnd3d12ddiCalcprivateblendstatesize0010; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivateblendstatesize0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDI_BLEND_DESC_0010 *
)
{...}

PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010 


```

## -remarks

## -see-also

