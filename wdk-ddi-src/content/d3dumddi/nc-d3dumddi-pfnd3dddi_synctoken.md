---
UID: NC:d3dumddi.PFND3DDDI_SYNCTOKEN
title: PFND3DDDI_SYNCTOKEN (d3dumddi.h)
description: The PFND3DDDI_SYNCTOKEN callback creates a sync token.
ms.assetid: 25c17000-b8cc-4e0f-a2ce-fe1c4a711413
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dumddi/PFND3DDDI_SYNCTOKEN"
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
- PFND3DDDI_SYNCTOKEN
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DDDI_SYNCTOKEN callback function

## -description

The PFND3DDDI_SYNCTOKEN callback creates a sync token.

## -prototype

```cpp
//Declaration

PFND3DDDI_SYNCTOKEN Pfnd3dddiSynctoken; 

// Definition

VOID Pfnd3dddiSynctoken 
(
	HANDLE hDevice
	 const D3DDDIARG_SYNCTOKEN *
)
{...}

```

## -parameters

### -param hDevice

A handle to the graphics context device.

### -param *

Pointer to a [D3DDDIARG_SYNCTOKEN](ns-d3dumddi-_d3dddiarg_synctoken.md) structure.

## -returns

Returns VOID.
