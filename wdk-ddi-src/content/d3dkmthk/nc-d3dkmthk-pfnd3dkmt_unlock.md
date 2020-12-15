---
UID: NC:d3dkmthk.PFND3DKMT_UNLOCK
title: PFND3DKMT_UNLOCK (d3dkmthk.h)
description: The PFND3DKMT_UNLOCK callback function unlocks a list of allocations.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_UNLOCK callback function"]
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
 - PFND3DKMT_UNLOCK
 - d3dkmthk/PFND3DKMT_UNLOCK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_UNLOCK
dev_langs:
 - c++
---

# PFND3DKMT_UNLOCK callback function


## -description

The PFND3DKMT_UNLOCK callback function unlocks a list of allocations.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_UNLOCK](ns-d3dkmthk-_d3dkmt_unlock.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_UNLOCK Pfnd3dkmtUnlock; 

// Definition

NTSTATUS Pfnd3dkmtUnlock 
(
	const D3DKMT_UNLOCK *
)
{...}

```

## -remarks

## -see-also

