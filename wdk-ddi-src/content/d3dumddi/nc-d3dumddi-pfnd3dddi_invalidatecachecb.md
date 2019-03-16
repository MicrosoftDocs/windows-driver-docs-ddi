---
UID: NC:d3dumddi.PFND3DDDI_INVALIDATECACHECB
title: PFND3DDDI_INVALIDATECACHECB (d3dumddi.h)
description: The PFND3DDDI_INVALIDATECACHECB callback function invalidates cache.
ms.assetid: 40e15cff-6522-47af-9dd3-232a7cf106ae
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dumddi.h
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
- d3dumddi.h
api_name: 
- PFND3DDDI_INVALIDATECACHECB
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DDDI_INVALIDATECACHECB callback function

## -description

The PFND3DDDI_INVALIDATECACHECB callback function invalidates cache.

## -prototype

```cpp
//Declaration

PFND3DDDI_INVALIDATECACHECB Pfnd3dddiInvalidatecachecb; 

// Definition

HRESULT Pfnd3dddiInvalidatecachecb 
(
	HANDLE hDevice
	 const D3DDDICB_INVALIDATECACHE *
)
{...}

```

## -parameters

### -param hDevice

A handle to the graphics context device.

### -param *

Pointer to a [D3DDDICB_INVALIDATECACHE](ns-d3dumddi-_d3dddicb_invalidatecache.md) structure.

## -returns

Returns HRESULT.
