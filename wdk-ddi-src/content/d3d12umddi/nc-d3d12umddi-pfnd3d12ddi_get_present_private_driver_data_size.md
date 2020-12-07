---
UID: NC:d3d12umddi.PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE
title: PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE (d3d12umddi.h)
description: Gets present private driver data size.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE callback function"]
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
 - PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE
 - d3d12umddi/PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE callback function


## -description

Gets present private driver data size.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_PRESENT_0001 structure.

## -returns

Returns UINT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE Pfnd3d12ddiGetPresentPrivateDriverDataSize; 

// Definition

UINT Pfnd3d12ddiGetPresentPrivateDriverDataSize 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_PRESENT_0001 *
)
{...}

PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE 


```

## -remarks

## -see-also

