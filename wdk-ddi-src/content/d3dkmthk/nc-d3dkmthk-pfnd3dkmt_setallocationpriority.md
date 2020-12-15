---
UID: NC:d3dkmthk.PFND3DKMT_SETALLOCATIONPRIORITY
title: PFND3DKMT_SETALLOCATIONPRIORITY (d3dkmthk.h)
description: The PFND3DKMT_SETALLOCATIONPRIORITY callback function sets the priority level of a resource or list of allocations.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETALLOCATIONPRIORITY callback function"]
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
 - PFND3DKMT_SETALLOCATIONPRIORITY
 - d3dkmthk/PFND3DKMT_SETALLOCATIONPRIORITY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETALLOCATIONPRIORITY
dev_langs:
 - c++
---

# PFND3DKMT_SETALLOCATIONPRIORITY callback function


## -description

The PFND3DKMT_SETALLOCATIONPRIORITY callback function sets the priority level of a resource or list of allocations.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETALLOCATIONPRIORITY](ns-d3dkmthk-_d3dkmt_setallocationpriority.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETALLOCATIONPRIORITY Pfnd3dkmtSetallocationpriority; 

// Definition

NTSTATUS Pfnd3dkmtSetallocationpriority 
(
	const D3DKMT_SETALLOCATIONPRIORITY *
)
{...}

```

## -remarks

## -see-also

