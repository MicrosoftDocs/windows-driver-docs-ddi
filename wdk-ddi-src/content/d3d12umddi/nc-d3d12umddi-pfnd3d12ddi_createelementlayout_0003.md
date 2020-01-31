---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEELEMENTLAYOUT_0003
title: PFND3D12DDI_CREATEELEMENTLAYOUT_0003 (d3d12umddi.h)
description: Creates an element layout.
ms.assetid: 23cc0136-45a0-4eb3-84e6-3c906b2bbca0
ms.date: 10/19/2018
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
 - "d3d12umddi/PFND3D12DDI_CREATEELEMENTLAYOUT_0003"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEELEMENTLAYOUT_0003
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATEELEMENTLAYOUT_0003 callback function

## -description

Creates an element layout.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATEELEMENTLAYOUT structure.

### -param Arg3

An element layout handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEELEMENTLAYOUT_0003 Pfnd3d12ddiCreateelementlayout0003; 

// Definition

VOID Pfnd3d12ddiCreateelementlayout0003 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATEELEMENTLAYOUT *
	 D3D12DDI_HELEMENTLAYOUT
)
{...}

PFND3D12DDI_CREATEELEMENTLAYOUT_0003 


```

