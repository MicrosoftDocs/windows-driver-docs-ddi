---
UID: NC:d3dkmthk.PFND3DKMT_ADJUSTFULLSCREENGAMMA
title: PFND3DKMT_ADJUSTFULLSCREENGAMMA (d3dkmthk.h)
description: The PFND3DKMT_ADJUSTFULLSCREENGAMMA callback function adjusts to full screen gamma.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_ADJUSTFULLSCREENGAMMA callback function"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_ADJUSTFULLSCREENGAMMA
 - d3dkmthk/PFND3DKMT_ADJUSTFULLSCREENGAMMA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_ADJUSTFULLSCREENGAMMA
dev_langs:
 - c++
---

# PFND3DKMT_ADJUSTFULLSCREENGAMMA callback function


## -description

The PFND3DKMT_ADJUSTFULLSCREENGAMMA callback function adjusts to full screen gamma.

## -parameters

### -param Arg1

[in] Pointer to a [D3DKMT_ADJUSTFULLSCREENGAMMA](ns-d3dkmthk-_d3dkmt_adjustfullscreengamma.md) structure.

## -returns

Returns NTSTATUS.

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

