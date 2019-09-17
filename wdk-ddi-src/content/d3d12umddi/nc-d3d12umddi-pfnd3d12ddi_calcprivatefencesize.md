---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEFENCESIZE
title: PFND3D12DDI_CALCPRIVATEFENCESIZE (d3d12umddi.h)
description: Calculate private fence size.
ms.assetid: 2a259064-aa18-4870-a52c-a58b6f650ba8
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
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATEFENCESIZE"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEFENCESIZE
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATEFENCESIZE callback function

## -description

Calculate private fence size.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATE_FENCE structure.

## -returns

Returns SIZE_T that.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEFENCESIZE Pfnd3d12ddiCalcprivatefencesize; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatefencesize 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_FENCE *
)
{...}

PFND3D12DDI_CALCPRIVATEFENCESIZE 


```

