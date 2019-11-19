---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYELEMENTLAYOUT
title: PFND3D12DDI_DESTROYELEMENTLAYOUT (d3d12umddi.h)
description: Destroy element layout.
ms.assetid: d980a8a5-a2ea-41a1-aaca-e8db6f646cf8
ms.date: 10/19/2018
ms.topic: callback
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
 - "d3d12umddi/PFND3D12DDI_DESTROYELEMENTLAYOUT"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROYELEMENTLAYOUT
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_DESTROYELEMENTLAYOUT callback function

## -description

Destroy element layout.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Element layout handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYELEMENTLAYOUT Pfnd3d12ddiDestroyelementlayout; 

// Definition

VOID Pfnd3d12ddiDestroyelementlayout 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HELEMENTLAYOUT
)
{...}

PFND3D12DDI_DESTROYELEMENTLAYOUT 


```

## -remarks

## -see-also

