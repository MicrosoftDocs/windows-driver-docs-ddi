---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEFENCESIZE
title: PFND3D12DDI_CALCPRIVATEFENCESIZE (d3d12umddi.h)
description: Calculate private fence size.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALCPRIVATEFENCESIZE callback function"]
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
 - PFND3D12DDI_CALCPRIVATEFENCESIZE
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEFENCESIZE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEFENCESIZE
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATEFENCESIZE callback function


## -description

Calculate private fence size.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

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

