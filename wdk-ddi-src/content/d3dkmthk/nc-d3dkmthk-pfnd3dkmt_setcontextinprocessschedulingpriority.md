---
UID: NC:d3dkmthk.PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY
title: PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY (d3dkmthk.h)
description: The PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY callback function sets the scheduling priority for a device context that is in the same process as other device contexts.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY callback function"]
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
 - PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY
 - d3dkmthk/PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY
dev_langs:
 - c++
---

# PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY callback function


## -description

The PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY callback function sets the scheduling priority for a device context that is in the same process as other device contexts.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY](ns-d3dkmthk-_d3dkmt_setcontextinprocessschedulingpriority.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY Pfnd3dkmtSetcontextinprocessschedulingpriority; 

// Definition

NTSTATUS Pfnd3dkmtSetcontextinprocessschedulingpriority 
(
	const D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY *
)
{...}

```

## -remarks

## -see-also

