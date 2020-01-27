---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001
title: PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001 (d3d12umddi.h)
description: Calculates the command signature size.
ms.assetid: 227d7c48-2d0d-48a9-ac1e-03a1e649685a
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
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001 callback function

## -description

Calculates the command signature size.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001 structure that contains the arguments to calculate a command signature size.

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001 Pfnd3d12ddiCalcPrivateCommandSignatureSize0001; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateCommandSignatureSize0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001 


```

## -remarks

## -see-also

