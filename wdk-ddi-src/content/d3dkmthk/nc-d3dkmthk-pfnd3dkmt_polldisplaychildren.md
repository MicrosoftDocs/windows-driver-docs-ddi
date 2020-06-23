---
UID: NC:d3dkmthk.PFND3DKMT_POLLDISPLAYCHILDREN
title: PFND3DKMT_POLLDISPLAYCHILDREN (d3dkmthk.h)
description: The PFND3DKMT_POLLDISPLAYCHILDREN callback function queries for connectivity status of all child devices of the given adapter.
ms.assetid: 198d78c5-7e56-4b14-a60e-ffef8447e169
ms.date: 10/19/2018
keywords: ["PFND3DKMT_POLLDISPLAYCHILDREN callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_POLLDISPLAYCHILDREN"
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
- PFND3DKMT_POLLDISPLAYCHILDREN
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_POLLDISPLAYCHILDREN callback function

## -description

The PFND3DKMT_POLLDISPLAYCHILDREN callback function queries for connectivity status of all child devices of the given adapter.

## -prototype

```cpp
//Declaration

PFND3DKMT_POLLDISPLAYCHILDREN Pfnd3dkmtPolldisplaychildren; 

// Definition

NTSTATUS Pfnd3dkmtPolldisplaychildren 
(
	const D3DKMT_POLLDISPLAYCHILDREN *
)
{...}

```

## -parameters

### -param  

Pointer to a [D3DKMT_POLLDISPLAYCHILDREN](ns-d3dkmthk-_d3dkmt_polldisplaychildren.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
