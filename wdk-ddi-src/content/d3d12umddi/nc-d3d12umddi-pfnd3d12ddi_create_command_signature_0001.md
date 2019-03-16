---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001
title: PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001 (d3d12umddi.h)
description: Create a command signature.
ms.assetid: 467a206c-9fe2-41c0-a264-05a80be53a6c
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001 callback function

## -description

Create a command signature.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001 Pfnd3d12ddiCreateCommandSignature0001; 

// Definition

HRESULT Pfnd3d12ddiCreateCommandSignature0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001 *
	 D3D12DDI_HCOMMANDSIGNATURE
)
{...}

PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param *

Pointer to a D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001 structure.

### -param D3D12DDI_HCOMMANDSIGNATURE: 

A handle to a command signature.

## -returns

Returns HRESULT.
