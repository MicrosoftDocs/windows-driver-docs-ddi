---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE
title: PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE (d3d12umddi.h)
description: Calculate private command allocator size.
ms.assetid: b194948b-29b1-453b-9254-06ae5b40ce96
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE callback function"]
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
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE callback function

## -description

Calculates private command allocator size.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATECOMMANDALLOCATOR structure.

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE Pfnd3d12ddiCalcprivatecommandallocatorsize; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatecommandallocatorsize 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATECOMMANDALLOCATOR *
)
{...}

PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE 


```

## -remarks

## -see-also

