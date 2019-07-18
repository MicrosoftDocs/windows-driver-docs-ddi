---
UID: NC:d3dkmthk.PFND3DKMT_ADJUSTFULLSCREENGAMMA
title: PFND3DKMT_ADJUSTFULLSCREENGAMMA (d3dkmthk.h)
description: The PFND3DKMT_ADJUSTFULLSCREENGAMMA callback function adjusts to full screen gamma.
ms.assetid: 0f0190e4-6c4a-4be7-8edb-e56faa25af69
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmthk/PFND3DKMT_ADJUSTFULLSCREENGAMMA"
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
- PFND3DKMT_ADJUSTFULLSCREENGAMMA
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_ADJUSTFULLSCREENGAMMA callback function

## -description

The PFND3DKMT_ADJUSTFULLSCREENGAMMA callback function adjusts to full screen gamma.

## -prototype

```cpp
//Declaration

PFND3DKMT_ADJUSTFULLSCREENGAMMA Pfnd3dkmtAdjustfullscreengamma; 

// Definition

NTSTATUS Pfnd3dkmtAdjustfullscreengamma 
(
	D3DKMT_ADJUSTFULLSCREENGAMMA *
)
{...}

```

## -parameters

### -param *

[in] Pointer to a [D3DKMT_ADJUSTFULLSCREENGAMMA](ns-d3dkmthk-_d3dkmt_adjustfullscreengamma.md) structure.

## -returns

Returns NTSTATUS.
