---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYKEYEDMUTEX
title: PFND3DKMT_DESTROYKEYEDMUTEX (d3dkmthk.h)
description: The PFND3DKMT_DESTROYKEYEDMUTEX callback function destroys keyed mutex.
ms.assetid: 35854482-8cd3-4d14-8f42-2917dfe134f2
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYKEYEDMUTEX callback function"]
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
 - PFND3DKMT_DESTROYKEYEDMUTEX
 - d3dkmthk/PFND3DKMT_DESTROYKEYEDMUTEX
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_DESTROYKEYEDMUTEX
dev_langs:
 - c++
---

# PFND3DKMT_DESTROYKEYEDMUTEX callback function


## -description

The PFND3DKMT_DESTROYKEYEDMUTEX callback function destroys keyed mutex.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_DESTROYKEYEDMUTEX](ns-d3dkmthk-_d3dkmt_destroykeyedmutex.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYKEYEDMUTEX Pfnd3dkmtDestroykeyedmutex; 

// Definition

NTSTATUS Pfnd3dkmtDestroykeyedmutex 
(
	const D3DKMT_DESTROYKEYEDMUTEX *
)
{...}

```

