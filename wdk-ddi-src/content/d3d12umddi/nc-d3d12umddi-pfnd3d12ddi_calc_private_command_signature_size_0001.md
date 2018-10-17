---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001
title: PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001
author: windows-driver-content
description: Calculates the command signature size.
ms.assetid: 227d7c48-2d0d-48a9-ac1e-03a1e649685a
ms.date: 
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001 callback function

## -description

Calculates the command signature size.

## -prototype

```
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

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param * 

Pointer to a D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001 structure that contains the arguments to calculate a command signature size.

## -returns

Returns SIZE_T.

## -remarks




## -see-also
