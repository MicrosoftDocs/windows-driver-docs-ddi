---
UID: NC:d3dkmthk.PFND3DKMT_GETCONTEXTSCHEDULINGPRIORITY
title: PFND3DKMT_GETCONTEXTSCHEDULINGPRIORITY (d3dkmthk.h)
description: The Pfnd3dkmtGetcontextschedulingpriority retrieves the scheduling priority for a device context.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETCONTEXTSCHEDULINGPRIORITY callback function"]
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
 - PFND3DKMT_GETCONTEXTSCHEDULINGPRIORITY
 - d3dkmthk/PFND3DKMT_GETCONTEXTSCHEDULINGPRIORITY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETCONTEXTSCHEDULINGPRIORITY
dev_langs:
 - c++
---

# PFND3DKMT_GETCONTEXTSCHEDULINGPRIORITY callback function


## -description

The Pfnd3dkmtGetcontextschedulingpriority retrieves the scheduling priority for a device context.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_GETCONTEXTSCHEDULINGPRIORITY](ns-d3dkmthk-_d3dkmt_getcontextschedulingpriority.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETCONTEXTSCHEDULINGPRIORITY Pfnd3dkmtGetcontextschedulingpriority; 

// Definition

NTSTATUS Pfnd3dkmtGetcontextschedulingpriority 
(
	D3DKMT_GETCONTEXTSCHEDULINGPRIORITY *
)
{...}

```

## -remarks

## -see-also

