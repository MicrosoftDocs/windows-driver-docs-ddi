---
UID: NC:d3dkmthk.PFND3DKMT_SETGAMMARAMP
title: PFND3DKMT_SETGAMMARAMP (d3dkmthk.h)
description: The PFND3DKMT_SETGAMMARAMP callback function sets the gamma ramp.
ms.assetid: 504b7ebc-5814-4c59-b9f4-0964e1e51f00
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETGAMMARAMP callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SETGAMMARAMP"
req.header: d3dkmthk.h
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
- d3dkmthk.h
api_name: 
- PFND3DKMT_SETGAMMARAMP
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SETGAMMARAMP callback function

## -description

The PFND3DKMT_SETGAMMARAMP callback function sets the gamma ramp.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETGAMMARAMP Pfnd3dkmtSetgammaramp; 

// Definition

NTSTATUS Pfnd3dkmtSetgammaramp 
(
	const D3DKMT_SETGAMMARAMP *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SETGAMMARAMP](ns-d3dkmthk-_d3dkmt_setgammaramp.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
