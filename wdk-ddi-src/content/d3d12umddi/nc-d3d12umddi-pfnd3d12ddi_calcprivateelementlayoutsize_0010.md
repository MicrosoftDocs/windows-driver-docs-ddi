---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010
title: PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010 (d3d12umddi.h)
description: The PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010 callback function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an element layout.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010 callback function"]
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
 - PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010 callback function


## -description

The CalcPrivateElementLayoutSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an element layout.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010 Pfnd3d12ddiCalcprivateelementlayoutsize0010; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivateelementlayoutsize0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATEELEMENTLAYOUT_0010 *
)
{...}

PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010 


```

## -remarks

## -see-also

