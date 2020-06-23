---
UID: NC:d3dkmthk.PFND3DKMT_FLUSHHEAPTRANSITIONS
title: PFND3DKMT_FLUSHHEAPTRANSITIONS (d3dkmthk.h)
description: The Pfnd3dkmtFlushheaptransitions callback function flushes heap transitions.
ms.assetid: a8ed0fbd-f4c0-48f9-94e7-e3ad531b59e0
ms.date: 10/19/2018
keywords: ["PFND3DKMT_FLUSHHEAPTRANSITIONS callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_FLUSHHEAPTRANSITIONS"
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
- PFND3DKMT_FLUSHHEAPTRANSITIONS
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_FLUSHHEAPTRANSITIONS callback function

## -description

The Pfnd3dkmtFlushheaptransitions callback function flushes heap transitions.

## -prototype

```cpp
//Declaration

PFND3DKMT_FLUSHHEAPTRANSITIONS Pfnd3dkmtFlushheaptransitions; 

// Definition

NTSTATUS Pfnd3dkmtFlushheaptransitions 
(
	D3DKMT_FLUSHHEAPTRANSITIONS *
)
{...}

```

## -parameters

### -param  

Pointer to a [D3DKMT_FLUSHHEAPTRANSITIONS](ns-d3dkmthk-_d3dkmt_flushheaptransitions.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
